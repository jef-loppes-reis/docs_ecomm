# Match Market Ads

O objetivo desse projeto, e clonar anuncios do Mercado Livre, sendo eles de lojas oficiais.
Basicamente e identinficar se o produto e o mesmo de tal loja oficial, seguindo alguns parametros.

![Tela principal](./imgs/tela_get_ad.png)

## Funcionalidades

1. [x] Baixar lista de lojas oficiais existentes no Mercado Livre;
2. [x] Abrir site geral das lojas oficiais, para categorias Acessórios para Veículos;
3. [x] Pega cada loja oficial da lista;
4. [x] Cruzar com nossa lista de marcas (usar FUZZY 60%) com nomes de loja oficiais;
5. [x] Validar manualmente e apontar a lista de marcas e os respectivos SKUs ativos;
6. [x] Pegar todos os produtos de uma determinada loja oficial, via HTML (WebScrapping);
7. [x] Pegar a lista do 4º passo, e avaliar o nível de matches, por cada categoria a seguir:
8. [x] GTIN (EAN) - Concorrente <=> GTIN (EAN) - SIAC;
9. [x] MPN - Concorrente <=> MPN – SIAC\Fraga;
10. [x] SKU – Concorrente <=> SKU – SIAC;
11. [x] OEM|MARCA – Concorrente <=> OEM|MARCA – SIAC;
12. [x] Criar uma planilha com os resultados acima;
13. [x] Baixar todos os atributos do anúncio concorrente, substituir os atributos padrões como: vídeo, fotos, código referencia (SKU), marca, descrição;
14. [x] Criar um Tkinter, para validacao das imagens;
15. [x] Subir as fotos validadas e ligar o anúncio;

## Mermeid

```mermaid
flowchart TD
    A[Start] -->|Read HTML| B([Get infos BeautifulSoup4])
    A -->|Read BD| C[(Query infos SIAC BD)]
    B -->|GET HTPP| D([Requests list codes MLB])
    D -->|GET API| E([Resquests MLB API])
    E --> F[(Created DataFrame)]
    F --> G{ETL Fuzzy infos MLB SIAC}
    C --> G
    G --> H[(DataFrame Results)]
    H --> I[Conferencia Humana]
    I --> J(Validacao dos produtos)
    I --> L(Validacao de imagens)
    J --> M(Cadastro dos produtos)
    L --> M
```

## Tabela

|mlb|gtin_ml|gtin_siac|gtin_fuzzy|mpn_ml|mpn_siac|mpn_fuzzy|
|---|-------|---------|----------|------|--------|---------|
|MLB4050163300|7899723815588|7899723815588|100%|ASHY24050|ASHY24050|100%|
|MLB3141414637|7899723833681|7899723833681|100%|BCVW20025|BCVW20J025|95%|
