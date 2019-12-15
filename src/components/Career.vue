<template>
    <div id="careerContainer">
        <div id="timelineContainer">
            <div
                v-for="(careerItem, index) in career.careerItem"
                v-bind:index="index"
                v-bind:key="careerItem.id"
                class="timelineItemContainer"
            >
                <span class="timelineDot"></span>
                <div class="careerTitle">{{careerItem.title}}</div>
                <div class="careerSubtitle">
                    <span>{{careerItem.establishment}}</span>,&nbsp;
                    <span>{{careerItem.location}}</span>
                </div>
                <div class="careerDates">
                    <span>{{careerItem.dateDebut}}</span>&nbsp;-&nbsp;
                    <span>{{careerItem.dateFin}}</span>
                </div>
                <div class="careerDescription">
                    {{careerItem.description}}
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    div#careerContainer {
        background: white;
        margin-top: 15px;
        padding: 35px 30px;
        max-width: 800px;
        margin-right: auto;
        margin-left: auto;
        box-shadow: 0 1px 4px rgba(0, 0, 0, .3);
        border-radius: 3px;
    }

    div.timelineItemContainer {
        position: relative;
        margin-left: 5px;
        padding-left: 20px;
        padding-bottom: 20px;
        border-left: 1px dashed black;
    }
    div.timelineItemContainer:last-child {
        border-left: none;
    }
    span.timelineDot {
        position: absolute;
        left: -6px;
        top: 0px;
        width: 11px;
        height: 11px;
        border-radius: 5px;
        background: white;
        border: 1px solid black;
    }
    div.timelineItemContainer:first-child {
        padding-top: 0px;
    }

    div.careerTitle {
        line-height: 1rem;
    }

    div.careerSubtitle {
        color: #b3b4b7;
        margin-top: 3px;
    }
    div.careerDates{
        color: #b3b4b7;
        font-size: 0.9rem;
    }
    div.careerDescription{
        font-size: 0.9rem;
        color :#666575;
    }
</style>

<script>

export default {
  name: 'Career',

  data: () => ({
    career: {
        careerItem: [
            {
                establishment: 'Polytech',
                title: 'Diplôme d\'Ingénieur en Informatique et Gestion',
                location: 'Montpellier',
                dateDebut: '2017',
                dateFin: '2020',
                description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
            },
            {
                establishment: 'IUT',
                title: 'DUT Informatique',
                location: 'Montpellier',
                dateDebut: '2015',
                dateFin: '2017',
                description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
            },
            {
                establishment: 'Lycée Frédéric Bazille',
                title: 'Baccalauréat Scientifique',
                location: 'Montpellier',
                dateDebut: '2012',
                dateFin: '2015',
                description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
            }
        ]
    }
  }),
};
</script>
