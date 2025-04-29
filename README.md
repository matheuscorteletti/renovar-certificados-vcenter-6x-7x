# Renovação de Certificados no vCenter 6.x e 7.x

Este repositório contém o script `fixcerts_3_2.py`, utilizado para renovar certificados expirados ou todos os certificados no vCenter 6.x e 7.x. A renovação de certificados é essencial para garantir a segurança e a continuidade das operações no vCenter.

---

## 🎯 Objetivo

O objetivo deste script é renovar os certificados de comunicação no vCenter. Ele permite:

- Renovar **apenas os certificados expirados**.
- Renovar **todos os certificados** do vCenter.
- Automatizar o processo, eliminando a necessidade de realizar todo o procedimento manualmente.

---

## 🛠️ Pré-requisitos

Antes de iniciar o processo, certifique-se de que você atende aos seguintes pré-requisitos:

1. vCenter 6.x ou 7.x.
2. Acesso ao vCenter via SSH com permissões administrativas.
3. Credenciais de **`administrator@vsphere.local`** para realizar a renovação dos certificados.
4. Backup completo do ambiente vCenter e dos certificados atuais.

---

## 🚀 Como Usar

### 1. Baixar o Script

Faça o download do repositório ou clone-o para o seu ambiente local:

```bash
git clone https://github.com/matheuscorteletti/renovar-certificados-vcenter-6x-7x.git
```

### 2. Fazer Upload para o vCenter

Após baixar o script, faça o upload do arquivo `fixcerts_3_2.py` para o vCenter. Utilize o comando `scp` para transferir o arquivo:

```bash
scp fixcerts_3_2.py usuario@vcenter:/caminho/destino/
```

### 3. Executar o Script

Acesse o vCenter via SSH e navegue até o diretório onde o script foi carregado. 

#### Renovar Apenas Certificados Expirados:
```bash
python /caminho/do/script/fixcerts_3_2.py replace --certType expired_only
```

#### Renovar Todos os Certificados:
```bash
python /caminho/do/script/fixcerts_3_2.py replace --certType all
```

Durante a execução, será solicitada a senha do **`administrator@vsphere.local`**. Insira a senha para proceder com a renovação.

### 4. Reiniciar o vCenter

Após a execução do script, reinicie o serviço do vCenter para aplicar as mudanças:

```bash
service vpxd restart
```

---

## ⚠️ Avisos Importantes

- **Backup:** Sempre faça backup do vCenter e dos certificados atuais antes de executar a renovação.
- **Interrupções:** A renovação pode causar uma breve interrupção na conectividade do vCenter.
- **Segurança:** Certifique-se de manter os novos certificados seguros e de seguir as melhores práticas de segurança.

---

## 📂 Estrutura do Repositório

- `fixcerts_3_2.py`: Script principal para renovação de certificados.

---

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir `issues` ou enviar `pull requests` para melhorar este repositório.


## 📞 Suporte

Caso tenha dúvidas ou problemas, entre em contato com o mantenedor do repositório ou abra uma [issue](https://github.com/matheuscorteletti/renovar-certificados-vcenter-6x-7x/issues).
