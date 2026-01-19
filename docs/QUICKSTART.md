# Guia Rápido - Hospedar App para Download

Este repositório está configurado para hospedar o aplicativo Vizzion Plus e disponibilizá-lo para download através do GitHub Releases.

## 🎯 O que foi configurado?

### ✅ Infraestrutura Completa

1. **README.md**: Página principal com:
   - Badges de release e downloads
   - Links de download direto
   - Descrição do app
   - Instruções de uso
   - Informações de contato

2. **Sistema de Releases**:
   - `RELEASES.md`: Histórico de versões
   - `.github/workflows/release.yml`: Automação de releases
   - Template de changelog

3. **Documentação**:
   - `docs/INSTALL_ANDROID.md`: Guia completo de instalação
   - `docs/FAQ.md`: Perguntas frequentes
   - `docs/FIRST_RELEASE.md`: Como criar o primeiro release

4. **Gestão do Projeto**:
   - `CONTRIBUTING.md`: Guia para contribuidores e processo de release
   - `LICENSE`: Licença MIT com disclaimer IPTV
   - `.gitignore`: Exclusão de arquivos de build
   - Issue templates para bugs e features

## 🚀 Como Usar - Passo a Passo

### 1. Prepare seu APK

Compile o aplicativo Vizzion Plus e gere o APK:

```bash
# Exemplo Flutter
flutter build apk --release

# Exemplo Android nativo  
./gradlew assembleRelease

# Renomeie o arquivo
mv app-release.apk vizzion-plus-v1.0.0.apk
```

### 2. Crie o Release no GitHub

#### Opção A: Via Interface Web (Recomendado para iniciantes)

1. Vá para: https://github.com/xcoretv/vizzion_plus/releases
2. Clique em **"Draft a new release"**
3. Preencha:
   - **Tag**: `v1.0.0` (criar nova tag)
   - **Title**: `Vizzion Plus v1.0.0`
   - **Description**: Copie do template em RELEASES.md
4. Anexe o APK: arraste `vizzion-plus-v1.0.0.apk`
5. Marque **"Set as the latest release"**
6. Clique em **"Publish release"**

#### Opção B: Via Git (Automático)

```bash
# 1. Atualize RELEASES.md com o changelog
# 2. Commit
git add RELEASES.md
git commit -m "docs: prepare release v1.0.0"
git push

# 3. Crie e envie a tag
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin v1.0.0
```

O workflow criará o release automaticamente. Depois, anexe o APK manualmente.

### 3. Verifique

- Acesse: https://github.com/xcoretv/vizzion_plus/releases
- Teste o download do APK
- Verifique se os badges no README estão atualizados

### 4. Divulgue

Compartilhe o link de download:
```
https://github.com/xcoretv/vizzion_plus/releases/latest
```

## 📋 Checklist para Cada Release

Antes de publicar uma nova versão:

- [ ] APK compilado e testado
- [ ] Versão incrementada corretamente (Semantic Versioning)
- [ ] RELEASES.md atualizado com changelog
- [ ] Código commitado e enviado ao GitHub
- [ ] Tag criada (formato: vX.Y.Z)
- [ ] Release publicado no GitHub
- [ ] APK anexado ao release
- [ ] Link de download testado
- [ ] Anúncio feito aos usuários

## 📁 Estrutura do Repositório

```
vizzion_plus/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.yml
│   │   └── feature_request.yml
│   └── workflows/
│       └── release.yml
├── docs/
│   ├── FAQ.md
│   ├── FIRST_RELEASE.md
│   └── INSTALL_ANDROID.md
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── RELEASES.md
```

## 🔄 Workflow de Release Automatizado

O arquivo `.github/workflows/release.yml` faz:

1. Detecta quando você faz push de uma tag (ex: v1.0.0)
2. Cria automaticamente um release no GitHub
3. Adiciona descrição padrão com links

**Você ainda precisa**: Anexar o APK manualmente após o release ser criado.

## 📝 Versionamento Semântico

Siga o padrão [SemVer](https://semver.org/):

- **v1.0.0** → Primeira versão estável
- **v1.0.1** → Correções de bugs (PATCH)
- **v1.1.0** → Novas funcionalidades (MINOR)
- **v2.0.0** → Mudanças incompatíveis (MAJOR)

## 🎨 Personalizações

### Mudar cores/tema do README

Edite os badges no topo do `README.md`:
```markdown
[![GitHub release](https://img.shields.io/github/release/xcoretv/vizzion_plus.svg?color=blue)](...)
```

### Adicionar mais plataformas

Para iOS, Windows, etc., adicione seções no `README.md`:
```markdown
### iOS
**[⬇️ Download IPA](https://github.com/xcoretv/vizzion_plus/releases/latest)**
```

### Customizar workflow

Edite `.github/workflows/release.yml` para:
- Mudar descrição padrão do release
- Adicionar build automático do APK
- Enviar notificações

## 📚 Documentos Importantes

- **Para usuários**: Leiam o [README.md](../README.md)
- **Para instalação**: [docs/INSTALL_ANDROID.md](INSTALL_ANDROID.md)
- **Para contribuir**: [CONTRIBUTING.md](../CONTRIBUTING.md)
- **Para primeiro release**: [docs/FIRST_RELEASE.md](FIRST_RELEASE.md)
- **Para dúvidas**: [docs/FAQ.md](FAQ.md)

## ❓ Perguntas Comuns

### Onde os usuários baixam o app?

Principalmente em: https://github.com/xcoretv/vizzion_plus/releases/latest

### Como atualizo o app depois?

Crie uma nova versão seguindo o mesmo processo, incrementando o número da versão.

### Posso hospedar em outros lugares?

Sim, mas o GitHub Releases é gratuito, confiável e não tem limites de download.

### E se eu quiser builds automáticos?

Configure GitHub Actions para compilar o APK automaticamente. Veja exemplos em `docs/FIRST_RELEASE.md`.

## 📞 Suporte

Dúvidas sobre esta configuração:
- Consulte [docs/FIRST_RELEASE.md](FIRST_RELEASE.md) para guia completo
- Abra uma [Discussion](https://github.com/xcoretv/vizzion_plus/discussions)
- Email: xcoreplaytv@gmail.com

---

**Pronto!** Seu repositório está configurado para hospedar e distribuir o Vizzion Plus. 🎉

Próximo passo: Criar seu primeiro release seguindo [docs/FIRST_RELEASE.md](FIRST_RELEASE.md)
