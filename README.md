# TempoExtra

Aplicativo Android para gestão de horas complementares, desenvolvido como trabalho acadêmico para o Projeto Integrador V do curso de Sistemas de Informação do Centro Universitário UNIFACEAR (2022).

**Autores:** Guilherme da Luz Weber e Mateus Chaves

**Orientador:** Prof. Rafael do Carmo Kerneski

A documentação completa do projeto está disponível em [docs/documentacao-projeto-integrador.docx](docs/documentacao-projeto-integrador.docx).

## Descrição

Muitas instituições de ensino não possuem uma plataforma unificada e simples para o acompanhamento de horas complementares. O TempoExtra foi criado para facilitar a visualização das horas complementares dos alunos e dos requerimentos enviados à instituição, além de permitir que os coordenadores de curso gerenciem esses requerimentos com facilidade.

O aplicativo permite que alunos enviem pedidos de validação de atividades complementares ao coordenador do seu curso. O coordenador analisa cada pedido e decide se ele é deferido, informando a quantidade de horas a ser creditada, ou indeferido. O saldo de horas do aluno é atualizado automaticamente.

O sistema possui três perfis de acesso:

- **Administrador:** cadastra os coordenadores.
- **Coordenador:** visualiza os pedidos recebidos e realiza o deferimento ou indeferimento.
- **Aluno:** realiza o próprio cadastro, envia pedidos e acompanha suas horas e a situação dos pedidos.

### Tipos de atividade

- Capacitação
- Produção Científica
- Atividades Humanísticas
- Vivência Profissional Complementar

## Estrutura do repositório

```
tempo-extra-android/
├── app/
│   ├── schemas/                      Esquemas exportados dos bancos de dados (Room)
│   └── src/main/
│       ├── java/com/example/tempoextra/
│       │   ├── data/                 Entidades, DAOs e bancos de dados (Room)
│       │   └── ui/                   Telas (Activities)
│       │       └── adapter/          Adaptadores e ViewHolders das listas
│       ├── res/                      Layouts, ícones e demais recursos
│       └── AndroidManifest.xml
├── docs/
│   └── documentacao-projeto-integrador.docx
├── gradle/wrapper/
├── build.gradle
└── settings.gradle
```

## Requisitos

- Android Studio
- JDK 17 (configurado em *Settings → Build Tools → Gradle → Gradle JDK*)
- Android SDK Platform 32 (Android 12L) e Build-Tools 33.0.0, instalados pelo *SDK Manager*
- Dispositivo ou emulador com Android 5.0 (API 21) ou superior

## Execução

1. Clone o repositório (`git clone https://github.com/Guilherme-Weber/tempo-extra-android.git`) e abra a pasta no Android Studio.
2. Aguarde a sincronização do Gradle.
3. Execute o módulo `app` em um emulador ou dispositivo conectado.

Para gerar o APK pelo terminal:

```
gradlew assembleDebug
```

O arquivo é gerado em `app/build/outputs/apk/debug/`.

Para gerar o APK de release (`TempoExtra-v1.1a-release.apk`, em `app/build/outputs/apk/release/`):

```
gradlew assembleRelease
```

O APK pronto para instalar também está disponível na página de [Releases](https://github.com/Guilherme-Weber/tempo-extra-android/releases). As mudanças de cada versão estão no [CHANGELOG.md](CHANGELOG.md).

## Utilização

1. Acesse com a conta de administrador e cadastre um coordenador, informando o curso.
2. Na tela inicial, cadastre um aluno vinculado ao mesmo curso.
3. Com a conta do aluno, abra um pedido informando o e-mail do coordenador, o tipo de atividade e a descrição.
4. Com a conta do coordenador, abra o pedido e defira-o (informando as horas) ou indefira-o.
5. Com a conta do aluno, consulte a situação dos pedidos e o total de horas.

Os dados são armazenados localmente no dispositivo.

## Tecnologias

- Java
- Android SDK (API 21 a 32) e Android Jetpack
- Room (persistência local em SQLite)
- RecyclerView e Material Components
- StyleableToast (mensagens de confirmação e erro)

## Documentação

O documento em [docs/documentacao-projeto-integrador.docx](docs/documentacao-projeto-integrador.docx) apresenta o processo completo de desenvolvimento: PM Canvas, análise de concorrência, requisitos, regras de negócio, diagramas de casos de uso, de classes e de entidade e relacionamento, além do protótipo das telas.
