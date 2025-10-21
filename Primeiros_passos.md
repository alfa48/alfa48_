# Primeiros passos
-- instalar uma máquina virtuar com o so kali: estou a usar o virtManager o sistema operativo da máquina fisica é linux mint
-- baixar o suposto virus na VM
-- executar o cmd, para procurar urls ou string suspeitas : strings arquivo_copy.exe | less
## Como assim uma máquina virtual nem sempre está isolado e o que são snapshots?

### Mesmo estando “dentro” do host, a VM costuma:
ter acesso à rede (Internet) via NAT ou bridge → pode contactar C2, baixar componentes ou espalhar-se;

partilhar pastas/áreas com o host (shared folders, clipboard, arrastar & soltar) → potencial de fuga;

manter dispositivos USB conectados → pode comunicar com hardware;

permitir que o host aceda ao disco virtual se não for protegido.

Para análise segura precisamos cortar essas ligações.

🧭 1️⃣ Ver todas as VMs conhecidas pelo libvirt
virsh list --all

1) Desligar/Remover a interface de rede da VM
virsh edit vmname
# remova ou comente o <interface>...</interface>, salve e saia

Procura texto “escondido” dentro do executável:
strings -n 8 arquivo.exe | less
Procura por:
URLs
Caminhos de diretórios (C:\Windows\System32)
Palavras como “password”, “key”, “token”, “HTTP”, “.dll”, etc.





sha256sum arquivo.exe, o que é gerar isso e como pode ajudar nesta situacao?
