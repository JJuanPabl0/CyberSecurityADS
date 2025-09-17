# 🛠️ Preparação dos Ambientes de Testes

> **Author:** Juan Pablo Silvério Silva

Esse é um relatório que mostra o processo de configuração do ambiente necessário para realização das práticas da disciplina de **Cybersecurity**.  
O ambiente é composto por máquinas virtuais com **Kali Linux** (máquina atacante) e **OWASP Broken Web Apps** (máquina alvo).

---


## 🔽 Download das Ferramentas

### 1. VirtualBox
O **VirtualBox** é uma ferramenta de virtualização de sistemas operacionais.  
Com ele é possível rodar o **Kali Linux** em um computador com Windows, sem comprometer o sistema principal.  
Isso garante segurança, já que qualquer teste será feito dentro de um ambiente isolado.  

🔗 [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)

---

### 2. OWASP Broken Web Apps
O **OWASP** (*Open Web Application Security Project*) é uma comunidade que fornece materiais e ferramentas sobre segurança de aplicações.  
Neste caso, utilizaremos a **OWASP Broken Web Apps**, uma máquina virtual com diversas aplicações vulneráveis para prática.  

🔗 [Download OWASP BWA](https://sourceforge.net/projects/owaspbwa/files/1.2/OWASP_Broken_Web_Apps_VM_1.2.ova/download)

➡️ Após o download, abra o VirtualBox e utilize a opção **IMPORT** para carregar o arquivo `.ova`.

---

### 3. Kali Linux
O **Kali Linux** é uma distribuição baseada no Debian voltada para **auditoria e testes de segurança**.  
Utilizaremos a versão em **máquina virtual pré-configurada para o VirtualBox**, evitando a instalação manual.  

🔗 [Download VM Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines)

➡️ Após o download, abra o VirtualBox e utilize o botão **+ (Add)** para adicionar o arquivo `.vbox`.

---

## ⚙️ Configuração do Ambiente Virtual

No VirtualBox:  
1. Clique em **Tools** → aba **Nat Networks**.  
2. Se não houver nenhuma rede NAT criada, clique em **Create** para gerar uma.  

### 🔌 Tipos de Rede no VirtualBox
- **NAT:** VM recebe IP virtual e acessa a internet via host.  
- **NAT Network:** cria rede virtual compartilhada entre várias VMs.  
- **Host Network:** VM se comunica diretamente com o host e rede externa.  
- **Bridge Network:** VM atua como dispositivo independente na rede, com IP próprio.  

---

## 🌐 Testando a Conexão entre as VMs

1. Ligue as duas VMs (Kali e OWASP).  
2. Acesse a VM **Kali Linux (Hacker)**:  
   - **Login:** `kali`  
   - **Senha:** `kali`  
3. No terminal, execute:  
   ```bash
   ip a
   ```
    Verifique se a VM recebeu um endereço IP.

4. Na VM OWASP (Web Server), ao iniciar será exibido um IP. Anote-o.
5. De volta ao Kali Linux, abra o navegador Firefox e acesse o IP da VM OWASP.
✅ Se a página de boas-vindas aparecer, significa que o ambiente está configurado corretamente.


![Tela de configuração da rede NAT](imagens/rede-nat.png)
![Página inicial OWASP no navegador Kali](imagens/owasp-pagina.png)


## 📝 Conclusão

Com esse ambiente configurado, temos a base necessária para realizar os próximos testes de segurança, incluindo SQL Injection, XSS, DoS, entre outros ataques, de forma segura e isolada.