### Плучение сертификатов
Playbook написан для получения wildcard сертификатов c DNS на cloudflare

### DNS
Документация по модулю cloudflare_dns https://docs.ansible.com/ansible/latest/modules/cloudflare_dns_module.html

##### Обязательные переменные
Создаем файл dns_tokens.yml в папке secret_files
'''bash
   ansible-vault create secret_files/dns_tokens.yml
'''
формат файла secret_files/dns_tokens.yml

    list_domains:
       example.com:
         email: it@example.com
         token: token_cloudflare

Запускаем командой
```bash
 $ ansible-playbook get_new_cert.yml --ask-vault-pass
```