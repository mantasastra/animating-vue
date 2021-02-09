<template>
  <div>
    <input type="text" placeholder="Name" v-model="newContact" />
    <button @click="addContact">Add Contact</button>
    <button @click="sortContacts">Sort</button>

    <transition-group tag="ul" name="slide-up" appear>
      <li v-for="contact in contacts" :key="contact">
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'List',
  data() {
    return {
      newContact: '',
      contacts: ['Ron Weasley', 'Harry Potter', 'Hermione Granger'],
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
      this.newContact = ''
    },
    sortContacts() {
      this.contacts = this.contacts.sort()
    },
  },
}
</script>

<style scoped></style>
