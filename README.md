# Script original by Crhisjd20 ( https://github.com/chrisjd20/hikvision_CVE-2017-7921_auth_bypass_config_decryptor )
# modificado por Alexandre C. Leite para mostrar diretamente a senha

Este script Python decodifica o arquivo de configuração de câmeras Hikvision suscetíveis a vulnerabilidade exposta no CVE-2017-7921.
(https://www.checkpoint.com/defense/advisories/public/2017/cpai-2017-0876.html/)

Basicamente, as câmeras hikvision que são vulneráveis ​​ao CVE listado acima podem ter várias coisas expostas usando uma simples string base64,
fornecida como argumento na url.

Por exemplo:  `http://<ip_da_camera>/System/configurationFile?auth=YWRtaW46MTEK`

Essa URL acima permite que um usuário não autenticado baixe o arquivo de configuração da câmera, que inclui informações do usuário. 
Este arquivo de configuração usa criptografia fraca e uma chave estática por padrão.

O script python fornecido irá descriptografar este arquivo de configuração para revelar a senha configurada na câmera.

Também forneço um arquivo de configuração de exemplo gerado para você testar.

# Como utilizar:

`python3 dec.py <nome_do_arquivo_baixado_da_camera>`


# Dependencias:

`sudo python3 -m pip install pycryptodome`

**Testado no Ubuntu 20.04 com python 3.8.5**
