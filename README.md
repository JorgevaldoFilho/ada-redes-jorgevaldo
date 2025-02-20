# ☁️ Projeto Ada - Redes: Relatório do Projeto 📋

## 🗺️ Planejamento

### 🧮 Cálculo das sub-redes:
Para o cálculo das sub-redes, é necessário utilizar a seguinte fórmula:
$$ 2^{32-n} - 2 \geq h, \text{ sendo n o número de bits usado para hosts na máscara da subnet e h o número de hosts} $$

Os departamentos seguem a seguinte configuração:

> - **Rede principal fornecida:** `10.100.0.0/20` (4096 endereços)
> - **Sub-redes a serem criadas para cada departamento:**
>     - **TI:** 100 hosts *(com possibilidade de expansão futura sem mudar IPs já atribuídos)*
>     - **Helpdesk:** 120 hosts
>     - **Recursos Humanos (RH):** 40 hosts
>     - **Inovação:** 50 hosts *(expansão futura para 129 no próximo ano)*
>     - **Vendas:** 300 hosts
>     - **Gerência:** 50 hosts

Veja um exemplo utilizando a fórmula para o departamento de **TI**:
- **TI**: $ 2^{32-n}-2 \geq 100 \therefore n=25 $

### 📄 Resultados das sub-redes:
Aplicando o mesmo procedimento do exemplo anteriormente apresentado, temos os seguintes resultados das sub-redes geradas:
1. TI = `10.100.0.0/25`, 128 endereços no total, 126 endereços disponíveis (endereço um pouco maior devido à expansão futura)
2. Helpdesk = `10.100.0.128/25`, 128 endereços no total, 126 endereços disponíveis
3. Recursos Humanos (RH) = `10.100.1.0/26`, 64 endereços no total, 62 endereços disponíveis
4. Inovação = `10.100.1.64/25`, 128 endereços no total, 126 endereços disponíveis (endereço um pouco maior devido à expansão futura para 129 no próximo ano)
5. Vendas = `10.100.2.0/23`, 512 endereços no total, 510 endereços disponíveis
6. Gerência = `10.100.4.0/26`, 64 endereços no total, 62 endereços disponíveis

## 🌐 Diagrama GNS3:
No projeto, há a pasta dos arquivos do diagrama em GNS3. Lá é possível encontrar detalhes dos itens e informações sobre as configurações utilizadas.
Para uma visualização mais ampla do projeto, a seguir está a estrutura do projeto:

```
├── gns3-diagrama-redes                                         # Diagrama do GNS3
│   ├── gns3-diagrama-redes.gns3                                # Arquivo principal do diagrama
│   ├── image                                                   # Pasta da imagem do roteador (deve-se seguir este padrão)
│   │   ├── c3725-adventerprisek9-mz.124-15.T14.image           
│   │   └── c3725-adventerprisek9-mz.124-15.T14.image.md5sum    
│   └── project-files                                           # Arquivos essenciais do diagrama
│       └── (...)
├── README.md                                                   # Relatório e guia do projeto (você está aqui :D)
└── validações                                                  # Pasta das validações em imagens
    └── (...)
```

## ✅ Validação:
Sobre a validação do projeto, é possível verificar através dos testes de conexão. Os comandos de testes foram:
- ping
- show ip interface brief
- show ip route

As validações (screenshots em `.png`) estão na seguinte localização `ada-redes-jorgevaldo/validações` deste projeto.

## ⚠️ Observações importantes:
Devido às limitações de envio, o arquivo de imagem do roteador não está contido na pasta deste projeto. Para utilizar o projeto, é necessário colocar a imagem no diretório correspondente `# Pasta da imagem do roteador`. É preferível que o nome da imagem seja: `c3725-adventerprisek9-mz.124-15.T14.image`.

---

Espero que tenha gostado do projeto!
Vida longa e próspera🖖😁🚀
