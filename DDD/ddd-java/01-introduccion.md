# Estructura
- app
    - main
        - resources
        - tv.codely.apps
            - backoffice
                - backend (Aqui pueden ir CLI , comandos)
                - frontend (Aqui pueden ir los controladores REST)
            - mooc
                - backend (Aqui pueden ir CLI , comandos, Scripts)
                - frontend (Aqui pueden ir los controladores REST)
                - command
                - controller
                    - courses
                        - CoursersController.java
    - tests
        - resources
        - tv.codely.apps
            - backoffice
                - backend (Aqui pueden ir CLI , comandos)
                - frontend (Aqui pueden ir los controladores REST)
            - mooc
                - backend (Aqui pueden ir CLI , comandos)
                - frontend (Aqui pueden ir los controladores REST)
- src
    - backoffice
        - main
        - test
    - mooc
        - main
            - tv.codely.mooc
                - videos
                    - application
                    - domain
                    - infraestructure
                - courses
                - shared
                - ...
        - test
            - tv.codely.mooc
                - videos
                - courses
                - shared
                - ...
    - shared
        - main
        - test
Helth check es un endpoint para ver que el servidor esta levantadosdfsdfkmjkj