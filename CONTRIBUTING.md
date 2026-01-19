# Guia de Contribuição

Obrigado por considerar contribuir com o Vizzion Plus! 

## 📋 Como Contribuir

### Reportando Bugs

1. Verifique se o bug já foi reportado nas [Issues](https://github.com/xcoretv/vizzion_plus/issues)
2. Se não encontrou, crie uma nova issue incluindo:
   - Descrição clara do problema
   - Passos para reproduzir
   - Comportamento esperado vs. atual
   - Screenshots (se aplicável)
   - Versão do app e do dispositivo
   - Logs de erro (se disponível)

### Sugerindo Melhorias

1. Abra uma issue com a tag `enhancement`
2. Descreva claramente a melhoria proposta
3. Explique por que seria útil para os usuários

### Pull Requests

1. Fork o repositório
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

## 🚀 Processo de Release

### Para Mantenedores

#### 1. Preparar Nova Versão

```bash
# Atualizar versão no código
# Atualizar RELEASES.md com changelog
git add .
git commit -m "chore: prepare release v1.0.0"
git push
```

#### 2. Criar Release no GitHub

1. Vá para [Releases](https://github.com/xcoretv/vizzion_plus/releases)
2. Clique em "Draft a new release"
3. Preencha os campos:
   - **Tag version**: `v1.0.0` (seguir [Semantic Versioning](https://semver.org/))
   - **Release title**: `Vizzion Plus v1.0.0`
   - **Description**: Copiar changelog do RELEASES.md
4. Anexar arquivos binários:
   - APK para Android: `vizzion-plus-v1.0.0.apk`
   - Outros builds conforme disponível
5. Marcar como "Latest release" se for a versão mais recente
6. Publicar release

#### 3. Formato de Nomes de Arquivo

- Android: `vizzion-plus-v{VERSION}.apk`
- Android (arm64): `vizzion-plus-v{VERSION}-arm64.apk`
- Android (armeabi-v7a): `vizzion-plus-v{VERSION}-armeabi-v7a.apk`
- Android (x86_64): `vizzion-plus-v{VERSION}-x86_64.apk`
- iOS: `vizzion-plus-v{VERSION}.ipa`

#### 4. Checklist de Release

- [ ] Versão atualizada no código
- [ ] RELEASES.md atualizado com changelog
- [ ] Builds testados em diferentes dispositivos
- [ ] Tag criada no Git
- [ ] Release publicada no GitHub
- [ ] Arquivos binários anexados
- [ ] README.md atualizado (se necessário)
- [ ] Anúncio feito (redes sociais, etc.)

## 📝 Padrões de Código

### Commits

Seguimos o padrão [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` Nova feature
- `fix:` Correção de bug
- `docs:` Mudanças na documentação
- `style:` Formatação, ponto e vírgula, etc.
- `refactor:` Refatoração de código
- `test:` Adicionar ou modificar testes
- `chore:` Manutenção, builds, etc.

Exemplos:
```
feat: adiciona suporte para EPG
fix: corrige crash ao carregar playlist M3U
docs: atualiza guia de instalação
```

## 🔍 Processo de Review

1. Todos os PRs precisam de pelo menos 1 aprovação
2. CI/CD deve passar (quando configurado)
3. Código deve seguir os padrões do projeto
4. Documentação deve ser atualizada se necessário

## 📞 Dúvidas?

- Abra uma [Discussion](https://github.com/xcoretv/vizzion_plus/discussions)
- Entre em contato: xcoreplaytv@gmail.com

## 📄 Licença

Ao contribuir, você concorda que suas contribuições serão licenciadas sob a mesma licença do projeto.
