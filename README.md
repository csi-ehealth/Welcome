# Welcome
⚠️<b>This organization uses Portuguese language, translate to use and access information</b>⚠️

CSI Ehealth é uma organização que possui dados de coletas pcap, códigos de extração e processamento de dados de sinais CSI WiFi do grupo eHealth do Laboratório Midiacom.

## Coleta de dados CSI

A execução do script de coleta (collectCSIdata.sh) deve ser realizado no Raspberry Pi
Os parâmetros do collectCSIdata.sh são:

1. Código do participante: Código numérico de três dígitos atribuído no momento do preenchimento do [FORMULÁRIO DE INFORMAÇÕES SOBRE PARTICIPANTE DA PESQUISA](https://docs.google.com/forms/d/e/1FAIpQLSeseYb5eHDGo0uwqmjdOMVPtJrJWfG7YyoD9ivlSHSSQe3toQ/viewform)

2. Código de atividade: As atividades definidas no [protocolo de coleta](https://docs.google.com/presentation/d/1Qd0f4cvgQdQkI0vefnRVrrMzth-kPpm4/edit#slide=id.p1) são formadas por três subcódigos posição_orientação_respiração, sendo os seguintes códigos:

    2.1 Código númerico
    * 0 - Representa uma coleta em vazio (sala sem presença do participante)
    * 1 - S_F_R
    * 2 - S_F_I
    * 3 - SL_F_R
    * 4 - S_C_R
    * 5 - S_C_I
    * 6 - P_F_R
    * 7 - P_F_I
    * 8 - P_C_R
    * 9 - P_C_I
    * 10 - D_F_R
    * 11 - D_F_I
    * 12 - D_C_R
    * 13 - D_C_I
    * 14 - DL_F_R
    * 15 - A_F_R
    * 16 - C_F_R
    * 17 - V_F_R

    2.2. Códigos de posição
    * de pé - P
    * sentado - S
    * deitado - D 
    * sentar e levantar - SL
    * deitar e levantar - DL
    * andar - A
    * correr - C
    * varrer - V

    2.3. Código de orientação
    * de frente para o Raspberry / deitado de costas na maca - F
    * de costas para o Raspberry / deitado de bruços na maca - C

    2.4. Código de respiração
    * respírando normalmente - R
    * respirando de maneira intervalada - I

    Por exemplo, caso queira realizar uma coleta de um participante na atividade deitado de bruços na maca respirando normalmente, o código formado será: D_C_R em numérico.

3. A largura de banda utilizada na rede Wi-Fi.

4. O canal utilizado na rede Wi-Fi.

5. O endereço MAC do dispositivo que realiza o ping

6. Número de amostras a serem coletadas

Para a coleta do participante 000, na atividade sentado de frente respirando intervalado, utilizando o testbed da Sala 534, que está com a rede Wi-Fi de 80 MHz de largura de banda, no canal 36, com o laptop de endereço MAC DC:53:60:11:66:92 executando o ping, caso queiramos obter 500 amostras do CSI, utilizamos o script da seguinte maneira:

sudo bash collectCSIdata.sh 000 2 80 36 DC:53:60:11:66:92 500

O resultado dessa coleta será a criação de um diretório com o código do participante abaixo do diretório scans e um arquivo .pcap cujo nome contém o código da atividade, o timestamp do início da coleta a informação da largura de banda e canal utilizados na captura. No caso do exemplo acima, caso a captura tenha sido realizada às 12h25m38s do dia 25/02/2022 teríamos a criação do arquivo: 

./scans/000/2_2022_02_25_-_12_25_38_bw_80_ch_36.pcap


Além da criação do arquivo, o script de coleta também envia o arquivo coletado ao desktop da sala, realizando um SCP, enviando para o diretório /home/midiacom/CSI e armazenando na mesma estrutura (/scans/000/2_2022_02_25_-_12_25_38_bw_80_ch_36.pcap)

# Versão DataSet

O DataSet está separado em duas versões de dados além das variações dos dispositivos de coletas, sendo:
* Data_DS1_(raspberry/Fabio_raspberry)
* Data_DS2_(raspberry/asus/Fabio_asus/Fabio_raspberry)

Sendo assim, possuindo juntamente dados relativos a coletas dos voluntários, com os equipamentos de medição de acurácia de modelos utilizados nos experimentos e estudos da tecnologia.

## Data_DS1

Contém os seguintes dados:
* Arquivos pcap de 500 pacotes.
* Ordem das posições: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17
* Arquivos do SmartWatch

## Data_DS2

Contém os seguintes dados:
* Arquivos pcap de 2000 pacotes.
* Ordem das posições: 1, 3, 4, 6, 8, 10, 12, 14, 2, 5, 7, 9, 11, 13, 15, 16, 17
* Arquivos do SmartWatch
* Arquivos da PolarBand

# Integridade

Para verificar a integridade na coletas de dados para cada dataset, cada um acompanha com um arquivo denominado <b>"faltas.txt"</b> que possui a marcação de coletas bem sucedidas e as faltas do mesmo.

# Acesso a Dados e Códigos

Para possuir acesso a dados ou códigos dos integrantes/grupo envie um email ao contato ou contate através da solicitação do próprio github.
