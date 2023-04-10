<template>
  <div class="team-container">
    <h1>Our Team</h1>
    <div class="team-members">
      <div v-for="member in teamMembers" :key="member.id" class="member-card">
        <img :src="member.avatar" :alt="member.name" class="avatar">
        <h2>{{ member.name }}</h2>
        <p>{{ member.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      teamMembers: [
        {
          id: 1,
          name: 'Cédric Brzyski',
          title: 'Frontend',
          avatar: 'profile.png',
        },
        {
          id: 2,
          name: 'Adrien Mussat',
          title: 'Frontend',
          avatar: 'profile.png',
        },
        {
          id: 3,
          name: 'Célian Adhuelo',
          title: 'Backend',
          avatar: 'profile.png',
        },
        {
          id: 4,
          name: 'Hugo Mouthino',
          title: 'Backend',
          avatar: 'profile.png',
        },
        {
          id: 5,
          name: 'Mathias Pinto',
          title: 'Backend',
          avatar: 'profile.png',
        },
      ]
    }
  }
}
</script>

<style>
.team-container {
  max-width: 960px;
  margin: 0 auto;
}

.team-members {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.member-card {
  max-width: 300px;
  margin: 16px;
  text-align: center;
}

.avatar {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
  object-position: center;
  margin: 0 auto;
  display: block;
}

.team-container h1 {
  padding: 20px;
}
</style>
