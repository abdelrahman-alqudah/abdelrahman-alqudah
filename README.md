<div align="center">

<img width="100%" src="profile-card.svg" alt="Abd Elrahman Alqudah, Software Engineer" />

<br/>

<a href="https://github.com/abdelrahman-alqudah">
  <img alt="Software Engineer building backend systems that fail predictably" src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1200&center=true&vCenter=true&width=700&color=2E6FD9&lines=Software+Engineer+%7C+Backend+Systems;Laravel+%26+ASP.NET+Core;Firestore+%2F+Cloud+Run+%2F+Cloud+Armor;Systems+that+fail+predictably" />
</a>

<br/><br/>

<a href="https://abdelrahmanalqudah.dev"><img src="https://img.shields.io/badge/Portfolio-0E2340?style=for-the-badge&logo=firefox&logoColor=F3D7C4" alt="Portfolio" /></a>
<a href="https://www.linkedin.com/in/abd-elarhman/"><img src="https://img.shields.io/badge/LinkedIn-0E2340?style=for-the-badge&logo=linkedin&logoColor=F3D7C4" alt="LinkedIn" /></a>
<a href="mailto:info@abdelrahmanalqudah.dev"><img src="https://img.shields.io/badge/Email-0E2340?style=for-the-badge&logo=gmail&logoColor=F3D7C4" alt="Email" /></a>
<a href="https://github.com/abdelrahman-alqudah"><img src="https://img.shields.io/badge/GitHub-0E2340?style=for-the-badge&logo=github&logoColor=F3D7C4" alt="GitHub" /></a>

</div>

<img src="divider.svg" width="100%" alt="" />

```bash
$ whoami
→ Software engineer. I design APIs, data models, and the infrastructure around them.
  Security isn't a checklist at the end. It's in the schema and the access rules
  from the first draft.
```

## Currently building: U JO RESIDENT

An end-to-end platform on Firebase and GCP, designed around the failure case first. Slow or failing dependencies stay off the request path, and nothing sensitive ever reaches the client.

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#0E2340','primaryTextColor':'#F3D7C4','primaryBorderColor':'#2E6FD9','lineColor':'#2E6FD9','secondaryColor':'#14213A','tertiaryColor':'#08111F','fontFamily':'ui-sans-serif, system-ui, sans-serif'}}}%%
flowchart LR
    Client([Client]) --> Armor{{Cloud Armor}}
    Armor --> API[API on Cloud Run]
    Secrets[(Secret Manager)] -.-> API
    API --> Queue[[Queue]]
    Queue --> Worker[Worker]
    Worker --> AI[AI model]
    AI --> Consumer[Consumer]
    Consumer --> DB[(Firestore)]
```

| Decision | Why |
| :-- | :-- |
| **Async pipeline** (queue → consumer) | One slow dependency can't take down the request path |
| **Firestore schema built around access patterns** | Security rules and queries shape the data model, not the other way round |
| **Cloud Run behind Cloud Armor** | Traffic is filtered at the edge before it reaches application code |
| **Secret Manager only** | Nothing sensitive in client code or in the repo |
| **AI calls routed through the API tier** | Model access is never exposed client-side |

## Tech stack

| | |
| :-- | :-- |
| **Backend** | ![Laravel](https://img.shields.io/badge/Laravel-0E2340?style=flat-square&logo=laravel&logoColor=F3D7C4) ![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-0E2340?style=flat-square&logo=dotnet&logoColor=F3D7C4) ![Entity Framework](https://img.shields.io/badge/Entity_Framework-0E2340?style=flat-square&logo=dotnet&logoColor=F3D7C4) ![REST](https://img.shields.io/badge/REST_APIs-0E2340?style=flat-square) ![JWT](https://img.shields.io/badge/JWT-0E2340?style=flat-square&logo=jsonwebtokens&logoColor=F3D7C4) ![OAuth2](https://img.shields.io/badge/OAuth2-0E2340?style=flat-square&logo=auth0&logoColor=F3D7C4) |
| **Languages** | ![C#](https://img.shields.io/badge/C%23-0E2340?style=flat-square&logo=csharp&logoColor=F3D7C4) ![PHP](https://img.shields.io/badge/PHP-0E2340?style=flat-square&logo=php&logoColor=F3D7C4) ![Go](https://img.shields.io/badge/Go-0E2340?style=flat-square&logo=go&logoColor=F3D7C4) ![Python](https://img.shields.io/badge/Python-0E2340?style=flat-square&logo=python&logoColor=F3D7C4) ![C++](https://img.shields.io/badge/C++-0E2340?style=flat-square&logo=cplusplus&logoColor=F3D7C4) ![Bash](https://img.shields.io/badge/Bash-0E2340?style=flat-square&logo=gnubash&logoColor=F3D7C4) |
| **Data** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0E2340?style=flat-square&logo=postgresql&logoColor=F3D7C4) ![MySQL](https://img.shields.io/badge/MySQL-0E2340?style=flat-square&logo=mysql&logoColor=F3D7C4) ![Redis](https://img.shields.io/badge/Redis-0E2340?style=flat-square&logo=redis&logoColor=F3D7C4) ![Firestore](https://img.shields.io/badge/Firestore-0E2340?style=flat-square&logo=firebase&logoColor=F3D7C4) |
| **Cloud** | ![Google Cloud](https://img.shields.io/badge/Google_Cloud-0E2340?style=flat-square&logo=googlecloud&logoColor=F3D7C4) ![Firebase](https://img.shields.io/badge/Firebase-0E2340?style=flat-square&logo=firebase&logoColor=F3D7C4) ![Cloud Run](https://img.shields.io/badge/Cloud_Run-0E2340?style=flat-square&logo=googlecloud&logoColor=F3D7C4) ![Cloud Armor](https://img.shields.io/badge/Cloud_Armor-0E2340?style=flat-square&logo=googlecloud&logoColor=F3D7C4) ![Secret Manager](https://img.shields.io/badge/Secret_Manager-0E2340?style=flat-square&logo=googlecloud&logoColor=F3D7C4) |
| **Delivery and security** | ![Docker](https://img.shields.io/badge/Docker-0E2340?style=flat-square&logo=docker&logoColor=F3D7C4) ![Terraform](https://img.shields.io/badge/Terraform-0E2340?style=flat-square&logo=terraform&logoColor=F3D7C4) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-0E2340?style=flat-square&logo=githubactions&logoColor=F3D7C4) ![SonarQube](https://img.shields.io/badge/SonarQube-0E2340?style=flat-square&logo=sonarqube&logoColor=F3D7C4) ![Snyk](https://img.shields.io/badge/Snyk-0E2340?style=flat-square&logo=snyk&logoColor=F3D7C4) |
| **Testing** | ![PHPUnit](https://img.shields.io/badge/PHPUnit-0E2340?style=flat-square&logo=php&logoColor=F3D7C4) ![Pest](https://img.shields.io/badge/Pest-0E2340?style=flat-square&logo=php&logoColor=F3D7C4) |

## What I do

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>Software engineering</h3>
      APIs with Laravel and ASP.NET Core, built for the failure case first.
    </td>
    <td width="50%" valign="top">
      <h3>System design</h3>
      Schemas, queues, and a clear line between cache and source of truth.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3>Infrastructure and security</h3>
      CI/CD, Cloud Armor, security rules, and secrets that live in a secrets manager instead of an <code>.env</code> committed by accident.
    </td>
    <td width="50%" valign="top">
      <h3>Database engineering</h3>
      PostgreSQL and Firestore schema design, query and index tuning, Redis caching.
    </td>
  </tr>
</table>

## GitHub stats

<div align="center">

<img width="49%" src="https://github-readme-stats.vercel.app/api?username=abdelrahman-alqudah&show_icons=true&theme=dark&title_color=D9B44A&icon_color=2E6FD9&text_color=B4C2DE&border_color=123A66&bg_color=060B18" alt="GitHub stats" />
<img width="49%" src="https://streak-stats.demolab.com?user=abdelrahman-alqudah&theme=dark&ring=2E6FD9&fire=D9B44A&currStreakLabel=D9B44A&sideLabels=B4C2DE&border=123A66&background=060B18" alt="GitHub streak" />

<img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=abdelrahman-alqudah&bg_color=060B18&color=B4C2DE&line=2E6FD9&point=F3D7C4&area=true&area_color=2E6FD9&title_color=D9B44A&border_color=123A66" alt="Contribution activity" />

</div>

<img src="divider.svg" width="100%" alt="" />

## Contact

<div align="center">

Amman, Jordan &nbsp;·&nbsp; [info@abdelrahmanalqudah.dev](mailto:info@abdelrahmanalqudah.dev) &nbsp;·&nbsp; [abdelrahmanalqudah.dev](https://abdelrahmanalqudah.dev)

</div>

> [!NOTE]
> Open to software engineering roles in backend, APIs, and system design. Remote-first, open to discussion. I respond within 24 hours.

<div align="center">
  <sub>Building systems with precision and purpose.</sub>
</div>
