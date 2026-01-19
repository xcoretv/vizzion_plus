# Guia de Instalação - Android

## 📱 Requisitos

- Android 5.0 (Lollipop) ou superior
- Mínimo 50 MB de espaço livre
- Conexão com a internet

## 📥 Método 1: Download Direto (Recomendado)

### Passo 1: Baixar o APK

1. Acesse a [página de releases](https://github.com/xcoretv/vizzion_plus/releases/latest)
2. Baixe o arquivo `vizzion-plus-vX.X.X.apk`
3. Aguarde o download concluir

### Passo 2: Habilitar Instalação de Fontes Desconhecidas

#### Android 8.0+ (Oreo e superior)

1. Abra **Configurações**
2. Vá para **Aplicativos e notificações** → **Avançado** → **Acesso especial a aplicativos**
3. Toque em **Instalar aplicativos desconhecidos**
4. Selecione o navegador ou gerenciador de arquivos que você usou para baixar o APK
5. Ative a opção **Permitir desta fonte**

#### Android 7.1 e inferior

1. Abra **Configurações**
2. Vá para **Segurança**
3. Ative a opção **Fontes desconhecidas**
4. Confirme tocando em **OK**

### Passo 3: Instalar o APK

1. Abra o aplicativo **Downloads** ou **Gerenciador de Arquivos**
2. Localize o arquivo `vizzion-plus-vX.X.X.apk`
3. Toque no arquivo para iniciar a instalação
4. Toque em **Instalar**
5. Aguarde a conclusão da instalação
6. Toque em **Abrir** para lançar o aplicativo

## 📥 Método 2: Via ADB (Para Desenvolvedores)

Se você tem o ADB instalado no seu computador:

```bash
# Conecte seu dispositivo via USB com depuração USB ativada
adb devices

# Instale o APK
adb install vizzion-plus-vX.X.X.apk

# Ou, se quiser atualizar mantendo os dados:
adb install -r vizzion-plus-vX.X.X.apk
```

## 🔄 Atualizando o App

### Atualização Manual

1. Baixe a nova versão do APK
2. Instale sobre a versão existente
3. Suas configurações e dados serão mantidos

### Verificar Atualizações

- Verifique regularmente a [página de releases](https://github.com/xcoretv/vizzion_plus/releases) para novas versões
- Recomendamos manter o app sempre atualizado para melhor desempenho e segurança

## ⚙️ Configuração Inicial

Após instalar o Vizzion Plus:

1. Abra o aplicativo
2. Escolha o método de configuração:
   - **Playlist M3U/M3U8**: Cole a URL ou selecione um arquivo local
   - **Xtream Codes**: Insira URL, usuário e senha

3. Exemplo de configuração M3U:
   ```
   http://seu-servidor.com/sua-playlist.m3u8
   ```

4. Exemplo de configuração Xtream Codes:
   ```
   URL: http://seu-servidor.com:porta
   Usuário: seu_usuario
   Senha: sua_senha
   ```

## 🛠️ Solução de Problemas

### O APK não instala

- ✅ Verifique se habilitou "Fontes Desconhecidas"
- ✅ Certifique-se de ter espaço suficiente no dispositivo
- ✅ Tente reiniciar o dispositivo
- ✅ Baixe o APK novamente (pode estar corrompido)

### App fecha ao abrir

- ✅ Verifique se seu Android é versão 5.0 ou superior
- ✅ Limpe o cache do app em Configurações → Apps → Vizzion Plus → Armazenamento
- ✅ Reinstale o aplicativo
- ✅ Verifique se tem memória RAM disponível

### Canais não carregam

- ✅ Verifique sua conexão com a internet
- ✅ Confirme que sua playlist/credenciais estão corretas
- ✅ Teste a playlist em outro player
- ✅ Entre em contato com seu provedor IPTV

### Vídeo trava ou congela

- ✅ Teste com uma conexão de internet mais rápida
- ✅ Reduza a qualidade de vídeo nas configurações (se disponível)
- ✅ Feche outros aplicativos rodando em segundo plano
- ✅ Limpe o cache do aplicativo

## 🔒 Segurança

- ⚠️ Baixe apenas da [página oficial de releases](https://github.com/xcoretv/vizzion_plus/releases)
- ⚠️ Não baixe de sites de terceiros
- ⚠️ Verifique o tamanho do arquivo e a assinatura
- ⚠️ Desabilite "Fontes Desconhecidas" após a instalação para maior segurança

## 📞 Suporte

Se encontrar problemas:

1. Consulte a seção [Solução de Problemas](#-solução-de-problemas)
2. Verifique as [Issues abertas](https://github.com/xcoretv/vizzion_plus/issues)
3. Crie uma nova issue com detalhes do problema
4. Entre em contato: xcoreplaytv@gmail.com

## 🔗 Links Úteis

- [Download](https://github.com/xcoretv/vizzion_plus/releases/latest)
- [Changelog](../RELEASES.md)
- [FAQ](FAQ.md)
- [Reportar Bug](https://github.com/xcoretv/vizzion_plus/issues/new)
