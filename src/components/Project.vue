<template>
    <div 
        :class="{
            'projectWrapper': true,
            'sm': $vuetify.breakpoint.sm,
            'xs': $vuetify.breakpoint.xs,
            }"
        
    >
        <div
            class="projectContainer"
            v-on:click="setProjectSelected(projectIndex)"
        >
            <div class="mainContentProject">
                <div class="projectName">
                    {{project.name}}
                </div>
                <div class="projectDates">
                    {{project.dateDebut}} - 
                    {{project.dateFin}}
                </div>
                <div class="projectKeywords">
                    <Keyword
                        v-for="(keyword, index) in project.keywords"
                        v-bind:index="index"
                        v-bind:key="index"
                        :keyword="keyword"
                        class="projectKeyword"
                    />
                </div>
                <div
                    v-bind:class="{
                        'projectDescription': true,
                        'focus': focused
                    }"
                    v-on:click="switchFocus"
                >
                    {{project.description}}
                </div>
            </div>
            <div class="projectLinks" v-if="project.links">
                <ProjectLink
                    v-for="(link, index) in project.links"
                    v-bind:index="index"
                    v-bind:key="index"
                    :link="link"
                />
            </div>
        </div>
    </div>
</template>

<style scoped>

    div.projectWrapper {
        top: 0;
        position: absolute;
        transition: 1s;
        width: 400px;
    }

    div.projectWrapper.sm {
        width: 350px!important;
        transition: 0.5s;
    }

    div.projectWrapper.xs {
        width: 300px!important;
        transition: 0.5s;
    }

    div.projectContainer {
        top: 0;
        background: white;
        transition: 1s;
        position: relative;
        left: -50%;
        box-shadow: 0 1px 4px rgba(0, 0, 0, .3);
        border-radius: 3px;
    }
    div.mainContentProject{
        padding: 10px;
    }
    div.projectLinks{
        background: #def1ff;
        border-radius: 0px 0px 3px 3px;
        padding: 10px 2px;
        display: flex;
        justify-content: center;
        overflow: hidden;
    }

    div.projectName{
        font-size: 1.5rem;
        text-align: center;
    }
    div.projectDates {
        text-align: center;
        line-height: 1rem;
        font-size: 0.8rem;
        color: #b3b4b7;
    }
    div.projectKeywords{
        text-align: center;
        margin-top: 5px;
    }
    div.projectDescription {
        cursor: pointer;
        margin-top: 15px;
        text-align: center;
        font-size: 0.9rem;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 5;
        -webkit-box-orient: vertical;
        background-color: white;
        transition: 0.5s;
    }
    .isPrimary div.projectDescription.focus {
        scale: 1.1;
        overflow: default;
        display: block;
        -webkit-line-clamp: none;
        box-shadow: 0 1px 4px rgba(0, 0, 0, .3);
    }
    div.projectWrapper.isPrimary {
        left: 50%;
    }

    div.projectWrapper.isNext {
        left: 70%;
    }

    div.projectWrapper.isPrevious {
        left: 30%;
    }

    div.projectWrapper.isFarAfter {
        left: 80%;
    }

    div.projectWrapper.isFarBefore {
        left: 20%;
    }
    div.projectWrapper.isVeryFarAfter {
        left: 83%!important;
    }

    div.projectWrapper.isVeryFarBefore {
        left: 17%!important;
    }

    div.isPrimary div.projectContainer  {
        opacity: 1;
        z-index: 10;
    }

    div.isNext div.projectContainer, div.isPrevious div.projectContainer  {
        scale : 0.9;
        opacity: 0.9;
        z-index: 5;
        cursor: pointer;
    }

    div.isFarAfter div.projectContainer, div.isFarBefore div.projectContainer{
        scale : 0.7;
        opacity: 0.4;
        z-index: 3;
        cursor: pointer;
    }
    div.isFarAfter.isVeryFarAfter div.projectContainer, div.isFarBefore.isVeryFarBefore div.projectContainer{
        opacity: 0!important;
        scale : 0.4!important;
        z-index: 1!important;
    }


</style>

<script>
import Keyword from './Keyword';
import ProjectLink from './ProjectLink';

export default {
  name: 'Project',   
  props: ['project', 'projectIndex', 'projectSelectedIndex'],
  components: {
      Keyword,
      ProjectLink
  },
  data: () => ({
      focused: false
  }),
  methods: {
    setProjectSelected: function(index){
        if(this.projectSelectedIndex !== this.projectIndex) {
            this.$parent.setProjectSelected(index);
            this.focused = false;
        }
    },
    switchFocus: function(){
        if(this.projectSelectedIndex == this.projectIndex) {
            this.focused = !this.focused;
        }
    }
  }

};
</script>
