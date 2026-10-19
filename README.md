# Central de Afiliados IA — MVP 1.0

Protótipo funcional, gratuito e sem backend: vitrine filtrável por Japão/Brasil, cadastro local de ofertas, importação/exportação JSON, simulador de comissões e assistente de textos **baseado em modelos locais** (não é IA generativa conectada).

## Teste

Abra `index.html` em um navegador. Para teste local mais fiel, no diretório execute `python3 -m http.server 8000` e acesse `http://localhost:8000`.

## Publicação gratuita

1. Crie conta no GitHub (sua autorização é necessária).
2. Crie repositório público e envie `index.html` (e opcionalmente os demais arquivos).
3. Em Settings > Pages, selecione Deploy from a branch, `main` e `/ (root)`; aguarde o endereço HTTPS publicado. A disponibilidade e os limites de planos gratuitos podem mudar.
4. **Importante:** o catálogo adicionado na aba Gerenciar usa `localStorage`: só aparece no navegador em que foi cadastrado. Para publicar um catálogo para todos os visitantes, edite o array `exemplos` no `index.html` com os produtos e links autorizados, ou exporte JSON e incorpore os registros nesse array antes de enviar a nova versão. A exportação sozinha não sincroniza o site.
5. Teste todos os links no site publicado, no celular e no desktop.

## Fluxo de automação atual

```
Cadastro manual de oferta autorizada
   → validação de URL HTTPS
   → armazenamento local
   → catálogo filtrável + links com rel=sponsored
   → visitante segue para checkout da loja parceira
   → comissão e relatórios ficam na plataforma afiliada
```

## Arquitetura futura (não incluída no MVP)

```
APIs/feeds oficiais de programas afiliados (com autorização)
    → rotina agendada (GitHub Actions / serviço compatível)
    → normalização de dados e checagem de links/preços
    → revisão humana e regras de compliance
    → catálogo publicado
    → análise de tráfego consentida
    → relatórios de comissão (quando API disponível)

Gerador de conteúdo com IA: integração opcional com provedor de LLM
    → chave guardada em servidor/secret manager, nunca em HTML público
    → revisão e aprovação humana
    → publicação via API autorizada
```

## Contas, permissões e custos

- **GitHub:** conta e autorização para hospedar. GitHub Pages pode hospedar o site estático sem custo dentro dos limites do serviço.
- **Programa afiliado japonês:** cadastro, aprovação e identificação de links válidos; por exemplo, programas de lojas ou redes de afiliados que atendam o Japão. Verifique elegibilidade, regras de divulgação, APIs e restrições de uso.
- **Programa afiliado brasileiro:** cadastro, aprovação e links rastreados válidos; confira elegibilidade fiscal e condições de cada rede.
- **IA generativa:** opcional; normalmente exige conta, chave de API e pode ter custo por uso. Não está ativada neste MVP.
- **Domínio próprio:** opcional e geralmente pago; use subdomínio gratuito da hospedagem no início.
- **Automação de posts:** opcional, depende de APIs oficiais e permissões das redes; não incluída.
- **Analytics:** opcional; avalie consentimento e regras de privacidade de Japão/Brasil antes de instalar cookies/trackers.
- **Pagamentos:** não são necessários para comissão de afiliado; o checkout ocorre na loja parceira.

## Cuidados antes de faturar

- Não há vendas, tráfego, conexão a programas, comissões ou receita garantida.
- Nunca divulgue links fictícios ou alegue preço/estoque atualizado sem verificação.
- Use aviso de publicidade e identificação de afiliados; respeite regras locais e dos programas.
- Não publique avaliações pessoais inventadas, imagens sem licença ou marcas usadas fora das regras do parceiro.
- Para uso comercial real, crie páginas de contato, política de privacidade e informações legais aplicáveis.
- Não coloque chaves, senhas, tokens ou dados privados no `index.html` ou no JSON público.

