# Clonador

Processo de clonar o produto, cadastro de forma explicita.

## Funcionalidades

### Aplicacao

Objeto para constroi a estrutura de descricao dos produtos, pega as aplicacoes dos veiculos
no sistema `SIAC` e `Fraga`, que vem de uma base de dados fornecidas pelos os dois sistemas.

#### Descricao

```python
# Titulo do produto

# Aplicacao de veiculos do produto

CARACTERÍSTICAS DO PRODUTO:
• Marca: # Marca do produto
• Código da peça: # Codigo de frabrica do produto
• Código de referência: # Lista de codigos de referencia do produto

CONTEÚDO DA EMBALAGEM:
• # Conteudo da embalgem, por exemplo: 1 Unidade, 1 KIT, 1 Par.

OBSERVAÇÃO:
• A Responsabilidade de confirmar a aplicação no veículo é exclusivamente do proprietário e do mecânico, uma vez que não temos acesso pessoal e visual da peça instalada.
• Nossos produtos têm garantia de fábrica de 3 meses. Não cobrimos má instalação ou mau uso do produto; recomendamos que a instalação seja feita por um profissional especializado.
• As compras realizadas em nome de Pessoa Jurídica podem estar sujeitas à cobrança de ICMS e DIFAL, conforme Protocolo ICMS 41, de 4 de Abril de 2008. Caso você tenha dúvidas sobre o percentual a ser aplicado, consulte a Cláusula Segunda, §1° do referido Protocolo.
• Para devolução por Defeito de Fabricação o produto deve acompanhar a Nota Fiscal de compra para sua identificação. Sem ela (Nota Fiscal), não é possível identificar o solicitante da Garantia.
• O produto deve ser devolvido nas mesmas condições em que foi enviado (na embalagem original, sem sinais de utilização para a perfeita condição de uso do próximo comprador).
• Caixa(s) e Imagem(s) Ilustrativa(s), meramente comercial para efeito estético e informativo de marca e modelo do anúncio.

NÚMERO INTERNO:
• # Codigo de referencia do produto no sistema SIAC [Codigo Interno].
```

### Compatibilidades

Objeto para clonar as compatibilidades de veiculos do produto, facilita muito e deixa o anuncios mais posicionado dentro da platafarma do market place.
E usado dentro do objeto principal, verifica se tem compatibilidades no antigo anuncio e cadastrado no novo.

### Clonagem

Obejto que executa a clonagem de forma explicita, faz o tratamentos dos codigos de referencias do produto, pega informacoes do produto a ser clonado, lista todos os atributos do produto como fotos e caracteristicas, cria um corpo padrao de cadastro para a API e posta do produto no Mercado Livre.

### Principal

Objeto principal executa de fato todos os outros objetos em um so modulo, carregando a planilha de conferencia do usuario verificando quais produtos tem o parametro chamado `Clona`, carrega a planilha de conferencia das imagens unindo com a planilha de produtos selecionando os produtos que tem todos os parametros validados como imagens e atributos
