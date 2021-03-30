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
    <NotesList
     :notes="notes"
    @remove="removeNote"/>
  </div>
</template>

<script>
import message from './components/Message'
import newNote from './components/NewNote'
import  NotesList from './components/NotesList'
export default {
  name: 'App',
  data: () => {
    return {
      message: null,
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
    }
  },
  components: {
    message,
    newNote,
    NotesList
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
</style>
