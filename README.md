# development-environment-linux

## docker
## docker compose
## terminal
### warp
🛠️ Etapa 1: Shell poderoso no VSCode
O Warp usa zsh por padrão. Vamos colocar o zsh com Oh My Zsh no VSCode pra começar com classe.

📦 Instalar zsh e Oh My Zsh
bash
Copy
Edit
sudo apt install zsh -y
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
Durante a instalação, ele já vai te perguntar se quer usar o zsh como shell padrão. Aceita.

🎨 Etapa 2: Tema com estilo (tipo Warp)
Vamos deixar o terminal estiloso, rápido e funcional.

🔥 Instalar o tema Powerlevel10k
bash
Copy
Edit
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
Edite o arquivo ~/.zshrc:

bash
Copy
Edit
ZSH_THEME="powerlevel10k/powerlevel10k"
Depois rode:

bash
Copy
Edit
source ~/.zshrc
Na primeira vez que abrir o terminal, ele vai iniciar um assistente de configuração visual. Personalize como preferir — bem moderno, estilo Warp.

🔌 Etapa 3: Plugins que turbinam
Edite novamente o ~/.zshrc e adicione os plugins:

bash
Copy
Edit
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
Depois instale eles:

bash
Copy
Edit
# Autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Syntax Highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
Rode:

bash
Copy
Edit
source ~/.zshrc
⚙️ Etapa 4: Configurar VSCode para usar esse terminal
No VSCode, abre as configurações em JSON (Ctrl + Shift + P > "Preferences: Open Settings (JSON)") e coloca:

json
Copy
Edit
"terminal.integrated.defaultProfile.linux": "zsh",
"terminal.integrated.profiles.linux": {
    "zsh": {
        "path": "/usr/bin/zsh"
    }
}
🧠 Bônus: Sugestão instantânea com estilo Warp
Se quiser algo ainda mais parecido com o Warp (sugestão de comandos em tempo real), pode instalar o atuin:

bash
Copy
Edit
curl -sSL https://raw.githubusercontent.com/atuinsh/atuin/main/install.sh | bash
atuin import auto
atuin sync
E adiciona no ~/.zshrc:

bash
Copy
Edit
eval "$(atuin init zsh)"

🎯 Diagnóstico: Por que os ícones não aparecem?
O Powerlevel10k depende de uma fonte Nerd Font com suporte a Powerline Glyphs, Devicons e outros símbolos especiais.

🛠️ Solução: Instalar e aplicar uma Nerd Font
1. Baixe a fonte recomendada
Vamos de MesloLGS Nerd Font, que é a oficial recomendada pelo Powerlevel10k.

Link direto:
🔗 Baixar MesloLGS NF

Baixe estas 4 variações (recomendo todas):

MesloLGS NF Regular

MesloLGS NF Bold

MesloLGS NF Italic

MesloLGS NF Bold Italic

2. Instale as fontes no sistema
Manualmente:
Dê dois cliques em cada arquivo .ttf baixado

Clique em “Instalar” para cada um

OU

Via terminal:
Copie para a pasta de fontes do usuário:

bash
Copy
Edit
mkdir -p ~/.local/share/fonts
cp ~/Downloads/"MesloLGS NF"*.ttf ~/.local/share/fonts/
fc-cache -fv
3. Configure o VSCode para usar essa fonte
No VSCode, abre as configurações JSON: Ctrl + Shift + P → Preferences: Open Settings (JSON)

Adiciona ou ajusta essa linha:

json
Copy
Edit
"terminal.integrated.fontFamily": "MesloLGS NF"
Pode ser necessário fechar e reabrir o VSCode pra aplicar corretamente.

4. Reconfigurar o Powerlevel10k (se quiser)
Se os ícones ainda estiverem quebrados, force a reconfiguração do tema com:

bash
Copy
Edit
p10k configure
Vai abrir o assistente gráfico. Se os ícones estiverem OK agora, segue com as configurações recomendadas (modo “fancy”, estilo Warp total).

🧠 Bônus: Verificar com segurança
Você pode testar manualmente se a fonte está funcionando com:

bash
Copy
Edit
echo "\uE0B0 \uE0B1 \uE0B2 \uE0B3 \uF09F \uF0E7 \uF0A0"
Se aparecer um monte de símbolos bonitões, tá no grau!


```
## nodejs