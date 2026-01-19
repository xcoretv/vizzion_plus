# Guia de Primeiro Release

Este guia orienta o processo de criação do primeiro release do Vizzion Plus no GitHub.

## 📋 Pré-requisitos

Antes de criar o primeiro release, certifique-se de ter:

- [ ] APK compilado e testado do Vizzion Plus
- [ ] Versão definida seguindo [Semantic Versioning](https://semver.org/) (ex: v1.0.0)
- [ ] Changelog preparado com as funcionalidades da versão
- [ ] Acesso de administrador ao repositório GitHub

## 🚀 Passo a Passo

### 1. Preparar o APK

Compile e teste seu APK:

```bash
# Exemplo para projeto Flutter
flutter build apk --release

# Exemplo para projeto Android nativo
./gradlew assembleRelease

# O APK geralmente estará em:
# Flutter: build/app/outputs/flutter-apk/app-release.apk
# Android: app/build/outputs/apk/release/app-release.apk
# Adapte o caminho conforme a estrutura do seu projeto
```

Renomeie o APK seguindo o padrão:
```bash
cp app-release.apk vizzion-plus-v1.0.0.apk
```

### 2. Atualizar Documentação

Atualize o arquivo `RELEASES.md`:

```markdown
## [1.0.0] - 2026-01-XX

### ✨ Novos Recursos
- Player IPTV com suporte M3U e M3U8
- Suporte para Xtream Codes API
- Interface moderna e intuitiva
- Organização de canais por categorias
- Sistema de favoritos
- EPG (Guia de Programação)

### 📱 Plataformas Suportadas
- Android 5.0+

### 📥 Downloads
- [Android APK](https://github.com/xcoretv/vizzion_plus/releases/download/v1.0.0/vizzion-plus-v1.0.0.apk)
```

### 3. Commit e Push

```bash
git add RELEASES.md
git commit -m "docs: update RELEASES.md for v1.0.0"
git push origin main
```

### 4. Criar Tag

```bash
# Criar tag anotada
git tag -a v1.0.0 -m "Release v1.0.0 - First public release"

# Push da tag
git push origin v1.0.0
```

**Nota**: Ao fazer push da tag, o workflow `.github/workflows/release.yml` será acionado automaticamente.

### 5. Criar Release no GitHub (Manual)

Se preferir criar manualmente ou se o workflow não executar:

1. Vá para: https://github.com/xcoretv/vizzion_plus/releases
2. Clique em **"Draft a new release"**
3. Preencha os campos:

   **Choose a tag**: `v1.0.0` (ou clique em "Create new tag")
   
   **Release title**: `Vizzion Plus v1.0.0`
   
   **Description**:
   ```markdown
   ## 🎉 Primeiro Release do Vizzion Plus!
   
   Esta é a primeira versão pública do Vizzion Plus, um player IPTV moderno para Android.
   
   ### ✨ Funcionalidades
   
   - ✅ Suporte para playlists M3U e M3U8
   - ✅ Compatível com Xtream Codes API
   - ✅ Interface moderna e intuitiva
   - ✅ Player de vídeo otimizado
   - ✅ Organização de canais por categorias
   - ✅ Sistema de favoritos
   - ✅ EPG (Guia de Programação Eletrônico)
   
   ### 📥 Download
   
   Baixe o APK para Android abaixo.
   
   ### 📱 Requisitos
   
   - Android 5.0 (Lollipop) ou superior
   - Mínimo 50 MB de espaço livre
   
   ### 📖 Instalação
   
   Consulte o [Guia de Instalação](https://github.com/xcoretv/vizzion_plus/blob/main/docs/INSTALL_ANDROID.md) para instruções detalhadas.
   
   ### ⚠️ Importante
   
   Este aplicativo não fornece conteúdo. Você deve ter suas próprias playlists M3U ou credenciais Xtream Codes.
   
   ### 🐛 Reportar Problemas
   
   Encontrou um bug? [Abra uma issue](https://github.com/xcoretv/vizzion_plus/issues/new/choose)
   
   ---
   
   **Changelog completo**: https://github.com/xcoretv/vizzion_plus/blob/main/RELEASES.md
   ```

4. **Anexar APK**:
   - Arraste e solte o arquivo `vizzion-plus-v1.0.0.apk` na área de anexos
   - Ou clique em "Attach binaries" e selecione o arquivo

5. **Configurações**:
   - ✅ Marque **"Set as the latest release"**
   - ⬜ NÃO marque "This is a pre-release" (apenas para versões beta)

6. Clique em **"Publish release"**

### 6. Verificar Release

Após publicar:

1. Acesse: https://github.com/xcoretv/vizzion_plus/releases
2. Verifique se o release aparece corretamente
3. Teste o link de download do APK
4. Verifique se os badges no README mostram a versão correta

### 7. Divulgar

Compartilhe a novidade:

- ✅ Redes sociais
- ✅ Fóruns e comunidades
- ✅ Website (se houver)
- ✅ Newsletter (se houver)

## 🔄 Releases Subsequentes

Para versões futuras, siga o mesmo processo ajustando:

- Número da versão (ex: v1.1.0, v1.0.1, v2.0.0)
- Changelog com as mudanças da versão
- Notas do release

## 📝 Exemplo de Versionamento

Seguindo [Semantic Versioning](https://semver.org/):

- **v1.0.0** → Primeira versão estável
- **v1.0.1** → Correção de bugs (PATCH)
- **v1.1.0** → Novas funcionalidades compatíveis (MINOR)
- **v2.0.0** → Mudanças incompatíveis (MAJOR)

## 🤖 Workflow Automático

O arquivo `.github/workflows/release.yml` automatiza a criação do release quando você faz push de uma tag:

```bash
# Criar e enviar tag
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin v1.0.0

# O GitHub Actions criará o release automaticamente
```

**Nota**: Você ainda precisará anexar o APK manualmente após o release ser criado pelo workflow, ou ajustar o workflow para incluir o build.

## 🛠️ Build Automatizado (Opcional)

Para automatizar o build do APK no workflow, você pode:

1. Adicionar secrets do keystore no GitHub
2. Configurar o workflow para compilar o APK
3. Fazer upload automático do APK para o release

Exemplo de job adicional no workflow:

```yaml
build-android:
  runs-on: ubuntu-latest
  steps:
    - name: Checkout code
      uses: actions/checkout@v4
    
    - name: Setup Java
      uses: actions/setup-java@v4
      with:
        distribution: 'zulu'
        java-version: '17'
    
    - name: Build APK
      run: |
        cd android
        ./gradlew assembleRelease
    
    - name: Upload APK to Release
      uses: softprops/action-gh-release@v1
      with:
        files: app/build/outputs/apk/release/app-release.apk  # Ajuste conforme sua estrutura
```

## ✅ Checklist Final

Antes de publicar o release, confirme:

- [ ] APK compilado e testado em dispositivos reais
- [ ] Versão atualizada no código do app
- [ ] RELEASES.md atualizado
- [ ] Tag criada e enviada
- [ ] Release publicado no GitHub
- [ ] APK anexado ao release
- [ ] Links de download testados
- [ ] README badges atualizados
- [ ] Divulgação feita

## 🔗 Links Úteis

- [Releases do Vizzion Plus](https://github.com/xcoretv/vizzion_plus/releases)
- [Semantic Versioning](https://semver.org/)
- [GitHub Releases Documentation](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

## 📞 Dúvidas?

Se tiver problemas ou dúvidas:

- Consulte a [documentação do GitHub](https://docs.github.com/)
- Abra uma [Discussion](https://github.com/xcoretv/vizzion_plus/discussions)
- Entre em contato: xcoreplaytv@gmail.com
