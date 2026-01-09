<div align="center">
  <!-- Banner -->
  <a href="https://n33miaz.github.io/n33miaz-links/#lumitcc"><img width="100%" src="https://github-stats-api.duckdns.org/api/banner?title=LumiLivre&subtitle=Library%20Management%20System&tag=(TCC)%20Bachelor%27s%20Thesis&title_color=762075&text_color=c9d1d9&v=1" /></a>

  <!-- Pins-->
  <a href="https://n33miaz.github.io/n33miaz-links/#lumiweb"><img src="https://github-stats-api.duckdns.org/api/pin?username=n33miaz&repo=lumilivre-web&custom_title=WebSite&bg_color=0d1117&title_color=762075&text_color=c9d1d9&icon_color=762075&hide_border=true&min_width=270&show_description=false" /></a>
  <a href="https://n33miaz.github.io/n33miaz-links/#lumiapp"><img src="https://github-stats-api.duckdns.org/api/pin?username=n33miaz&repo=lumilivre-app&custom_title=Application&bg_color=0d1117&title_color=762075&text_color=c9d1d9&icon_color=762075&hide_border=true&min_width=270&show_description=false" /></a>
  <a href="https://n33miaz.github.io/n33miaz-links/#lumiapi"><img src="https://github-stats-api.duckdns.org/api/pin?username=n33miaz&repo=lumilivre-api&custom_title=API%20Restfull&bg_color=0d1117&title_color=762075&text_color=c9d1d9&icon_color=762075&hide_border=true&min_width=270&show_description=false" /></a>
</div>

<br/>

<div align="center">
  <h1>Sobre o Projeto</h1>
</div>

O **LumiLivre** é um ecossistema completo desenvolvido para modernizar a administração de bibliotecas escolares e incentivar a leitura. Centralizamos processos manuais em uma plataforma unificada, conectando bibliotecários e estudantes de forma eficiente.

- **WebSite**: Painel de controle para bibliotecários gerenciarem acervo, alunos e empréstimos. 
- **Application**: Vitrine digital para alunos consultarem o catálogo e reservarem livros. 
- **API RestFull**: Cérebro da aplicação. Gerencia regras de negócio, segurança e dados.

<br/>

<div align="center">
  <h1>Arquitetura do Sistema</h1>
</div>

Utilizamos uma arquitetura cliente-servidor moderna baseada em microsserviços e nuvem para garantir escalabilidade.

```mermaid
flowchart TD
    classDef mobile fill:#02569B,stroke:#fff,stroke-width:2px,color:#fff;
    classDef web fill:#61DAFB,stroke:#fff,stroke-width:2px,color:#000;
    classDef api fill:#762075,stroke:#fff,stroke-width:2px,color:#fff;
    classDef db fill:#336791,stroke:#fff,stroke-width:2px,color:#fff;
    classDef storage fill:#3ECF8E,stroke:#fff,stroke-width:2px,color:#fff;
    classDef external fill:#ddd,stroke:#333,stroke-width:1px,color:#000,stroke-dasharray: 5 5;

    UserMobile["Application (Aluno)"]:::mobile
    UserWeb["WebSite (Bibliotecário)"]:::web
    
    subgraph Cloud["-"]
        direction TB
        API["API RestFull"]:::api
        DB[("PostgreSQL")]:::db
        Storage["Supabase Storage"]:::storage
    end
    
    External["Google Books / BrasilAPI"]:::external

    UserMobile -->|REST API / JSON| API
    UserWeb -->|REST API / JSON| API
    
    API -->|JPA / Hibernate| DB
    API -->|Upload Capas e PDF's| Storage
    API -.->|Consulta Metadados| External
```

<div align="center">
  <sub>LumiLivre © 2025 - Todos os direitos reservados.</sub>
</div>
