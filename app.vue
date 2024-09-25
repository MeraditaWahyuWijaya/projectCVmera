<template>
  <div class="cv">
    <header>
      <div class="header-left">
        <img :src="profileImage" alt="Profile Picture" class="profile-image" />
      </div>
      <div class="header-right">
        <h1>{{ name }}</h1>
        <p>{{ jobTitle }}</p>
        <p>{{ contactInfo }}</p>
        <p>{{ bio }}</p>
      </div>
    </header>

    <section>
      <h2>Education</h2>
      <ul>
        <li v-for="edu in education" :key="edu.institution">
          <h3>{{ edu.degree }}</h3>
          <p>{{ edu.institution }} - {{ edu.dates }}</p>
        </li>
      </ul>
    </section>

    <section>
      <h2>Work Experience</h2>
      <ul>
        <li v-for="job in experience" :key="job.company">
          <h3>{{ job.position }}</h3>
          <p>{{ job.company }} - {{ job.dates }}</p>
          <p>{{ job.description }}</p>
        </li>
      </ul>
    </section>

    <section>
      <h2>Organizational Experience</h2>
      <ul>
        <li v-for="org in orgExperience" :key="org.organization">
          <h3>{{ org.position }}</h3>
          <p>{{ org.organization }} - {{ org.dates }}</p>
          <p>{{ org.description }}</p>
        </li>
      </ul>
    </section>

    <section>
      <h2>Skills</h2>
      <ul>
        <li v-for="skill in skills" :key="skill">{{ skill }}</li>
      </ul>
    </section>

    <!-- Committees Section -->
    <section>
      <h2>Committees</h2>
      <ul>
        <li v-for="committee in committees" :key="committee.title">
          <h3>{{ committee.title }}</h3>
          <p>{{ committee.event }} - {{ committee.year }}</p>
          <p>{{ committee.description }}</p>
        </li>
      </ul>
    </section>

    <!-- New Section: Other Expertises -->
    <section>
      <h2>Other Expertises</h2>
      <ul>
        <li v-for="expertise in otherExpertises" :key="expertise">{{ expertise }}</li>
      </ul>
    </section>
  </div>
</template>

<script setup>
const name = 'Meradita Wahyu Wijaya';
const jobTitle = 'Freelance Graphic Designer';
const contactInfo = 'Email: meraditaw@gmail.com | Phone: +62 882 3262 0117';
const profileImage = 'mera.jpg'; // Replace with the correct image path
const bio = 'A student of the Faculty of Vocational Information Technology who has expertise in managing social media, creating visual content, editing videos, and creating UI/UX designs. Skilled in communication, cooperation, time management, and problem solving.';

const education = [
  {
    degree: 'Information Technology',
    institution: 'University of Brawijaya',
    dates: '2023 - Present'
  },
  {
    degree: 'Multimedia',
    institution: 'SMK N 1 Wonosobo',
    dates: '2014 - 2018'
  }
];

const experience = [
  {
    position: 'Freelance',
    company: 'Fiverr',
    dates: 'Jun 2023 - Present',
    description: 'Serve customers in creating advertising poster designs and promotional materials on demand, serve 5-10 customer orders every month related to 2D and 3D design, including logo creation, illustrations, 3D models, and animations.'
  },
  {
    position: 'Design And Marketing',
    company: 'Serena.id',
    dates: 'Nov 2022 - Mar 2023',
    description: 'Create a frame design for photo printing, contribute in creating designs according to customer requests, manage social media accounts, including posting content, responding to comments and messages.'
  },
  {
    position: 'Graphic Designer',
    company: 'Javaprint Digital Printing',
    dates: 'Mar 2022 - Jun 2022',
    description: 'Produce 10+ banner, vandal, and photo print designs daily according to demand. Communicate with customers to understand their needs and preferences.'
  }
];

const orgExperience = [
  {
    position: 'Multimedia',
    organization: 'Digital Creative Raden Patah Mosque',
    dates: '2024 - 2025',
    description: 'Collaborate with other team members for planning and execution of activities.'
  },
  {
    position: 'Member',
    organization: 'Formation (English Speaking Student Forum)',
    dates: '2023',
    description: 'Collaborate with other team members for planning and execution of activities.'
  },
  {
    position: 'Puskominfo Staff and Creative Economy Delegation',
    organization: 'HIMA Information Technology',
    dates: '2023 - 2024',
    description: 'Manage the Information Technology Study Program Instagram account to post documentation and publications.'
  }
];

const skills = [
  'Corel Draw', 
  'Adobe Illustrator', 
  'Adobe After Effect', 
  'Figma', 
  'Blender', 
  'Adobe Premiere'
];

const committees = [
  {
    title: 'Event division staff',
    event: 'CREANOMIC',
    year: '2024',
    description: 'Responsible for brainstorming and developing the event concept and theme. Collaborate with other teams to create a clear event plan and timeline. Ensure that all event goals, objectives, and messages are clearly communicated.'
  },
  {
    title: 'Livestream Digital Creative',
    event: 'Kajian KISMALA Raden Patah Mosque',
    year: '2024',
    description: 'Broadcast live the speech that is being carried out on various platforms such as YouTube, Instagram, and TikTok.'
  }
];

const otherExpertises = [
  'Non-Technical Skills: Collaboration, Communication, Time Management, Problem Solving.', 
  'Languages: Indonesian (Speaker), English (Intermediate).', 
  'Software: Microsoft Office (Word, Excel, PowerPoint), Adobe Premiere, Figma, Blender, Coreldraw, Adobe Photoshop.', 
];
</script>

<style>
.cv {
  max-width: 800px;
  margin: auto;
  padding: 20px;
  background-color: #EFBC9B;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(255, 255, 255, 0.1);
}

header {
  display: flex;
  align-items: center;
  margin-bottom: 30px;
}

.header-left {
  flex-shrink: 0;
  margin-right: 20px;
}

.profile-image {
  width: 130px;
  height: 160px;
  border-radius: 0%;
}

.header-right {
  flex-grow: 1;
}

h1 {
  font-size: 2.5em;
  margin: 0;
}

h2 {
  border-bottom: 2px solid #ffffff;
  padding-bottom: 5px;
  margin-top: 20px;
  color: #8D493A;
}

section {
  margin-bottom: 20px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 10px;
  padding: 10px;
  background-color: #f7eeee;
  border: 1px solid #ffffff;
  border-radius: 5px;
}

li h3 {
  margin: 0;
  color: #8D493A;
}

p {
  margin: 5px 0;
  color: #333333;
}
/* Gaya untuk Nama */
h1 {
  font-size: 2em;
  margin: 0;
  color: #fffdfe; /* Warna pink yang mencolok untuk nama */
  text-transform: uppercase; /* Huruf kapital untuk nama */
  font-weight: thick;
  letter-spacing: 2px; /* Spasi antar huruf */
  text-shadow: 2px 2px 5px rgba(255, 105, 180, 0.4); /* Bayangan teks pink */
}

/* Gaya untuk Job Title */
.header-right p:nth-of-type(1) {
  font-size: 1.5em;
  margin-top: 10px;
  color: #8D493A; /* Warna pink lebih lembut untuk job title */
  font-style: italic;
}

/* Gaya untuk Contact Info */
.header-right p:nth-of-type(2) {
  font-size: 1.2em;
  color: #8D493A; /* Warna pink medium untuk informasi kontak */
  margin-bottom: 10px;
}

/* Gaya untuk Bio (Deskripsi Diri) */
.header-right p:nth-of-type(3) {
  font-size: 1.1em;
  color: #8D493A; /* Warna pink terang untuk deskripsi diri */
  line-height: 1.6; /* Spasi antar baris agar lebih mudah dibaca */
  background-color: #F8EDE3; /* Latar belakang pink muda untuk bio */
  padding: 10px;
  border-radius: 8px;
  border: 2px solid #F8EDE3; /* Border pink lembut */
  box-shadow: 0 2px 5px rgba(255, 182, 193, 0.3); /* Bayangan lembut */
}

</style>
