# renovar-certificados-vcenter-6x-7x
# Renovação de Certificados no vCenter 6.x e 7.x

Este repositório contém o script **fixcerts_3_2.py**, utilizado para renovar os certificados expirados ou todos os certificados no vCenter 6.x e 7.x. A renovação de certificados é um processo importante para garantir a segurança e a continuidade das operações no vCenter.

## Objetivo

O objetivo deste script é renovar os certificados de comunicação no vCenter. Ele oferece a capacidade de renovar apenas os certificados expirados ou todos os certificados do vCenter, sem necessidade de realizar todo o processo manualmente.

## Pré-requisitos

1. **vCenter 6.x ou 7.x**.
2. Acesso ao vCenter via SSH com permissões administrativas.
3. Acesso ao **administrator@vsphere.local** para realizar a renovação dos certificados.
4. **Backup** completo do ambiente vCenter e dos certificados atuais.

## Como Usar

### 1. Baixar o Script

Para obter o script, faça o download do repositório ou clone-o para o seu ambiente:

git clone https://github.com/matheuscorteletti/renovar-certificados-vcenter-6x-7x.git

Fazer Upload para o vCenter
 
Após baixar o script, faça o upload do arquivo fixcerts_3_2.py para o vCenter.

Você pode usar o scp para copiar o arquivo para o vCenter:
scp fixcerts_3_2.py usuario@vcenter:/caminho/destino/
3. Executar o Script
Acesse o vCenter via SSH e navegue até o diretório onde o script foi carregado.

Renovar Apenas Certificados Expirados:


python /caminho/do/script/fixcerts_3_2.py replace --certType expired_only

Renovar Todos os Certificados:


python /caminho/do/script/fixcerts_3_2.py replace --certType all

4. Solicitação de Senha
Quando solicitado, insira a senha do administrator@vsphere.local para proceder com a renovação.

5. Reiniciar o vCenter
Após a execução do script, reinicie o vCenter para aplicar as mudanças:


service vpxd restart
Avisos Importantes
Backup: Sempre faça backup do vCenter e dos certificados atuais antes de executar a renovação.

Interrupções: A renovação dos certificados pode causar uma breve interrupção na conectividade do vCenter.

Segurança: Certifique-se de manter os novos certificados seguros e de seguir as melhores práticas de segurança.
