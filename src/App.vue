<template>
  <div id="app">
    <h1>My NotePad</h1>

    <!--    new note-->
    <newNote
    :newNote="newNote"
    @addNote="addNote"/>

    <!--    message-->
    <message
    v-if="message"
    :message="message"/>

    <!--    note list-->
    <div class="list__hedaer">
      <div class="title__left">
		  <p>Мои заметки</p>
<!--		  search-->
		  <search
		:value="search"
		@search="search = $event"/>
	  </div>

      <div class="icon">
        <svg width="18px" height="18px" class="view__block" :class="{ active: !grid }" @click="grid = false" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
             viewBox="0 0 22.105 22.105" style="enable-background:new 0 0 22.105 22.105;" xml:space="preserve">
<g>
	<path d="M5.535,6.02c0.076,0,0.137-0.062,0.137-0.137V0.236c0-0.075-0.061-0.136-0.137-0.136H0.139C0.062,0.1,0,0.161,0,0.236
		v5.647C0,5.958,0.062,6.02,0.139,6.02H5.535z"/>
  <path d="M13.75,6.02c0.076,0,0.137-0.062,0.137-0.137V0.236c0-0.075-0.061-0.136-0.137-0.136H8.355
		c-0.078,0-0.138,0.061-0.138,0.136v5.647c0,0.075,0.061,0.137,0.139,0.137H13.75z"/>
  <path d="M21.967,16.084H16.57c-0.078,0-0.137,0.062-0.137,0.138v5.646c0,0.077,0.059,0.137,0.137,0.137h5.396
		c0.074,0,0.139-0.06,0.139-0.137v-5.646C22.105,16.147,22.041,16.084,21.967,16.084z"/>
  <path d="M13.805,13.983c0.076,0,0.139-0.062,0.139-0.137V8.2c0-0.077-0.062-0.138-0.139-0.138H8.408
		C8.332,8.062,8.27,8.123,8.27,8.2v5.646c0,0.075,0.062,0.137,0.139,0.137H13.805z"/>
  <path d="M13.861,16.084H8.463c-0.076,0-0.139,0.062-0.139,0.138v5.646c0,0.077,0.062,0.137,0.139,0.137h5.398
		c0.072,0,0.135-0.06,0.135-0.137v-5.646C13.996,16.147,13.934,16.084,13.861,16.084z"/>
  <path d="M5.643,16.084H0.244c-0.076,0-0.135,0.062-0.135,0.138v5.646c0,0.077,0.059,0.137,0.135,0.137h5.398
		c0.074,0,0.137-0.06,0.137-0.137v-5.646C5.779,16.147,5.717,16.084,5.643,16.084z"/>
  <path d="M21.914,13.983c0.074,0,0.137-0.062,0.137-0.137V8.2c0-0.077-0.062-0.138-0.137-0.138h-5.398
		c-0.074,0-0.135,0.061-0.135,0.138v5.646c0,0.075,0.061,0.137,0.135,0.137H21.914z"/>
  <path d="M21.857,6.02c0.078,0,0.139-0.062,0.139-0.137V0.236c0-0.075-0.06-0.136-0.139-0.136h-5.395
		c-0.076,0-0.139,0.061-0.139,0.136v5.647c0,0.075,0.062,0.137,0.139,0.137H21.857z"/>
  <path d="M5.588,13.983c0.078,0,0.137-0.062,0.137-0.137V8.2c0-0.077-0.059-0.138-0.137-0.138H0.193
		c-0.078,0-0.137,0.061-0.137,0.138v5.646c0,0.075,0.059,0.137,0.137,0.137H5.588z"/>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
  <g>
	</g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
</svg>
        <svg width="20px" height="20px" class="view__list" :class="{ active: grid }" @click="grid = true" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
             viewBox="0 0 60.123 60.123" style="enable-background:new 0 0 60.123 60.123;" xml:space="preserve">
<g>
	<path d="M57.124,51.893H16.92c-1.657,0-3-1.343-3-3s1.343-3,3-3h40.203c1.657,0,3,1.343,3,3S58.781,51.893,57.124,51.893z"/>
  <path d="M57.124,33.062H16.92c-1.657,0-3-1.343-3-3s1.343-3,3-3h40.203c1.657,0,3,1.343,3,3
		C60.124,31.719,58.781,33.062,57.124,33.062z"/>
  <path d="M57.124,14.231H16.92c-1.657,0-3-1.343-3-3s1.343-3,3-3h40.203c1.657,0,3,1.343,3,3S58.781,14.231,57.124,14.231z"/>
  <circle cx="4.029" cy="11.463" r="4.029"/>
  <circle cx="4.029" cy="30.062" r="4.029"/>
  <circle cx="4.029" cy="48.661" r="4.029"/>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
          <g>
</g>
</svg>
      </div>
    </div>
    <NotesList
     :notes="notesFilter"
    @remove="removeNote"
    :grid="grid"/>
  </div>
</template>

<script>
import message from './components/Message'
import newNote from './components/NewNote'
import NotesList from './components/NotesList'
import Search from './components/Search'

export default {
  name: 'App',
  data () {
    return {
      message: null,
	  search: '',
      grid: false,
      newNote:{
        title: '',
        description: '',
        date: new Date(Date.now()).toLocaleString()
      },
      notes: [
        {
          title: 'Первая заметка',
          description: 'Описание для первой заметки',
          date: new Date(Date.now()).toLocaleString()
        },
        {
          title: 'Вторая заметка',
          description: 'Описание для второй заметки',
          date: new Date(Date.now()).toLocaleString()
        },
      ],
    }
  },
    computed: {
        notesFilter () {
            let array = this.notes,
                search = this.search
            if (!search) return array
            // Small
            search = search.trim().toLowerCase()
            // Filter
            array = array.filter(function (item) {
                if (item.title.toLowerCase().indexOf(search) !== -1) {
                    return item
                }
            })
            // Error
            return array
        }
    },
  methods: {
    addNote(){
      if(this.newNote.title === ''){
        this.message = 'Заголовок пустой'
        return false
      }

      this.notes.push({
        title: this.newNote.title,
        description: this.newNote.description,
        date: this.newNote.date,

      })
      this.message = null

      this.newNote.title = ''
      this.newNote.description = ''
    },
    removeNote(index){
      this.notes.splice(index, 1)
    },
  },
  components: {
    message,
    newNote,
    NotesList,
    Search
  }
}
</script>

<style lang="scss" >
  @import '/src/assets/scss/null.scss';
  @import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');
*{
  font-family: 'Nunito', sans-serif
}
  #app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
body{
  background-color: #eeeeee !important;
}

h1{
  font-size: 25px;
  margin-top: 20px;
  margin-bottom: 20px;
  text-align: center;
}

.list__hedaer{
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 80%;
  margin: auto;
    margin-top: 30px;
  .title__left{
    font-size: 24px;
    color: black;
	display: flex;
  }
}

.view__list{
  cursor: pointer;
}

.view__block{
  margin-right: 10px;
  cursor: pointer;
}

    svg{
        fill: #999999;
        &.active{
            fill: #550fdc;
        }
    }
</style>
