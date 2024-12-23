## Entidades Envolvidas:

- Comprador (Pessoa Física)
- Vendedor (Pessoa Física)
- Advogado
- Cartório de Registro de Imóveis [(ONR)](https://www.registrodeimoveis.org.br/intranet/arquivos/upload/geral/999999_upload_de_arquivos_geral_20230906_144922_7926cdd0-fda3-4122-8b8c-c408c7c708f1.pdf)
- Cartório de Notas
- Prefeitura Municipal (Recife)

## Diagrama de Sequência

```mermaid
    sequenceDiagram
    participant V as Vendedor
    participant A as Advogado
    participant C as Comprador
    participant CN as Cartório Notas
    participant CRI as Cartório Registro
    participant P as Prefeitura

    Note over V,A: Fase 1: Contratação e Documentação Inicial
    V->>A: Contrata serviços jurídicos
    Note right of V: Docs Vendedor:<br/>- RG e CPF<br/>- Certidão casamento/nascimento<br/>- Comprovante residência<br/>- Matrícula atualizada do imóvel<br/>- IPTU 2024 quitado
    C->>A: Contrata serviços jurídicos
    Note right of C: Docs Comprador:<br/>- RG e CPF<br/>- Certidão casamento/nascimento<br/>- Comprovante residência<br/>- Comprovante de renda

    Note over A,P: Fase 2: Análise e Certidões
    A->>P: Solicita certidões municipais
    Note right of A: Certidões necessárias:<br/>- Negativa débitos municipais<br/>- Negativa débitos federais<br/>- Certidão distribuição<br/>- Certidão de ônus reais
    P->>A: Emite certidões

    Note over A,C: Fase 3: Contrato e ITBI
    A->>C: Elabora contrato promessa
    C->>V: Assina contrato e paga sinal
    A->>P: Solicita guia ITBI
    P->>A: Emite guia
    C->>P: Paga ITBI

    Note over V,CRI: Fase 4: Escritura e Registro
    A->>CN: Agenda escritura
    Note right of CN: Docs para escritura:<br/>- Docs pessoais V e C<br/>- Certidões atualizadas<br/>- ITBI pago<br/>- Guia do IPTU
    V-->>CN: Comparece para assinar
    C-->>CN: Comparece para assinar
    CN->>CRI: Envia para registro

    Note over V,C: Fase 5: Conclusão
    C->>V: Efetua pagamento final
    CRI->>C: Entrega matrícula atualizada
    V->>C: Entrega chaves
```
