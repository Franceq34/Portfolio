<template>
    <div id="projectsContainer">
        <div id="projectsList">
            <Project
                v-for="(project, index) in projects"
                :project="project"
                :projectIndex="index"
                :projectSelectedIndex="projectSelected"
                v-bind:index="index"
                v-bind:key="index"
                v-bind:class="{
                    'isVeryFarBefore': index < projectSelected - 2,
                    'isFarBefore': index < projectSelected - 1,
                    'isPrevious': index == projectSelected - 1,
                    'isPrimary': index == projectSelected,
                    'isNext': index == projectSelected + 1,
                    'isFarAfter': index > projectSelected + 1,
                    'isVeryFarAfter': index > projectSelected + 2
                    }"
            />
        </div>
    </div>
</template>

<style scoped>

    .projectCarouselIcon{
        width: 50px;
        cursor: pointer;
    }
    .projectCarouselIcon.disabled{
        opacity: 0.5;
        cursor: default!important;
    }
    .previousIcon{
        transform: rotate(180deg);
    }
    div#projectsList {
        position: relative;
        width: 100%;
    }

</style>

<script>
import Project from './Project';

export default {
  name: 'Projects',

  components: {
    Project
  },
  
  methods: {
    setProjectSelected: function (index) {
        this.projectSelected = index;
    }
  },

  data: () => ({
    projectSelected: 0,
    projects: [
        {
            name: 'Projet Alpha',
            dateDebut: '12/19',
            dateFin: '02/20',
            keywords: [
                {
                    name: 'Vue'
                },
                {
                    name: 'Node'
                },
                {
                    name: 'PostgreSQL'
                }
            ],
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
            applicant: 'UMR Selmet Supagro',
            links: [
                {
                    name: 'Github',
                    icon: './icons/github',
                    disabled: false
                },
                {
                    name: '1',
                    icon: './icons/github',
                    disabled: false
                }
            ]
        },
        {
            name: 'Applications Inter-Opérables',
            dateDebut: '10/19',
            dateFin: '11/20',
            keywords: [
                {
                    name: 'React'
                },
                {
                    name: 'Node'
                },
                {
                    name: 'PostgreSQL'
                }
            ],
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
            applicant: 'Polytech Montpellier',
            links: [
                {
                    name: '40h',
                    icon: './icons/github',
                    disabled: false,
                    title: 'Temps passé'
                },
                {
                    name: '4',
                    icon: './icons/github',
                    disabled: false,
                    title: '4 collaborators'
                }
            ]
        },
        {
            name: 'SGIT',
            dateDebut: '10/19',
            dateFin: '11/20',
            keywords: [
                {
                    name: 'Scala'
                },
                {
                    name: 'Git'
                }
            ],
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
            applicant: 'Polytech Montpellier',
            links: [
                {
                    name: '50h',
                    icon: './icons/github',
                    disabled: false,
                    title: 'Temps passé'
                },
                {
                    name: 'Github',
                    icon: './icons/github',
                    disabled: false,
                    adress: 'https://github.com/Franceq34/SGIT',
                    title: 'Github'
                }
            ]
        },
        {
            name: 'Aircraft Recognition System',
            dateDebut: '06/19',
            dateFin: '09/19',
            keywords: [
                {
                    name: 'Unity3D'
                },
                {
                    name: 'C#'
                }
            ],
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
            applicant: 'Bangkok University MIT',
            links: [
                {
                    name: '4',
                    icon: './icons/github',
                    disabled: false,
                    title: '4 images'
                }
            ]
        },
        {
            name: 'Projet Data Science',
            dateDebut: '01/19',
            dateFin: '02/19',
            keywords: [
                {
                    name: 'R'
                },
                {
                    name: 'Shiny'
                },
                {
                    name: 'HTML'
                }
            ],
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
            applicant: 'Mutuelle de motards',
            links: [
                {
                    name: '10h',
                    icon: './icons/github',
                    disabled: false,
                    title: 'Temps passé'
                },
                {
                    name: 'Visiter',
                    icon: './icons/github',
                    disabled: false,
                    adress: 'https://polytechig4.shinyapps.io/mutuelle/',
                    title: 'Visiter'
                },
                {
                    name: 'Github',
                    icon: './icons/github',
                    disabled: false,
                    adress: 'https://github.com/Franceq34/Mutuelle',
                    title: 'Github'
                },
                {
                    name: '2',
                    icon: '',
                    disabled: false,
                    title: 'Collaborateurs'
                }
            ]
        },
        {
            name: 'MyColoc',
            dateDebut: '06/18',
            dateFin: '08/18',
            keywords: [
                {
                    name: 'Angular'
                },
                {
                    name: 'HTML'
                },
                {
                    name: 'CSS'
                }
            ],
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
            applicant: 'Polytech Montpellier',
            links: [
                {
                    name: '120h',
                    icon: './icons/github',
                    disabled: false,
                    title: 'Temps passé'
                },
                {
                    name: 'Github',
                    icon: './icons/github',
                    disabled: false,
                    adress: 'https://github.com/Franceq34/MyColoc',
                    title: 'Github'
                }
            ]
        }
    ]
  }),
};
</script>
