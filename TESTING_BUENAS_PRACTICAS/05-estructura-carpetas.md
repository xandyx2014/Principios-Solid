# Estructura de carpetas
- applications
    - backoffice_backend
    - backoffice_frontend
    - mooc_backend
    - mooc_frontend
- src
    - Backoffice
        - Videos
            - Infraestructure
            - Aplication
            - Domain
        - ...
        - Shared
    - Mooc
        - Videos
        - Courses
        - Shared
        - ...
        - Roadmap
        - Shared
    - Shared (Cosas compartidas entre los modulos, la configuracion Injection Dependencia, Base de datos connection)
        - Domain
        - Infraestructure
- tests
    - aplications
        - backoffice_backend
        - backoffice_frontend
        - mooc_backend
        - mooc_frontend
    - src
        - Backoffice
        - Mooc
            - Videos
                - application
                    - VideosSearcherSould
                - domain
                    - VideoCategoryMother
                    - VideoCreatedMother
                    - VideoIdMother
                    - VideoMother
                    - VideoTitleMother
                - infraestructura
                    - dependecy_injection
                    - marshaller
                    - repository
                        - DoobieMysqlVideoRepositoryShould
                        - VideoRepositoryMock
                    - VideoIntegrationTestCase
            - Courses
            - Shared
            - ..
            - Roadmap
        - Shared