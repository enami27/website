<template>
  <div class="container">
    <header class="header">
      <h1 class="title">Imane Benyettou</h1>
      <p class="subtitle">MIAGE Student based in Bordeaux, France</p>
      <nav class="nav">
        <a href="https://substack.com/@imanebn" target="_blank">Substack</a> | 
        <a href="https://github.com/enami27" target="_blank">GitHub</a> |
        <a href="https://www.linkedin.com/in/imanebenyettou" target="_blank">Linkedin</a>
      </nav>
    </header>

    <main class="main">
      <section class="section">
        <h2 class="section-title">Summary</h2>
        <p>Currently pursuing a degree in Mathematics and Computer Science (MIAGE) at the University of Bordeaux, with a specialization in data analysis and problem-solving methodologies. This program combines technical expertise with practical business acumen.</p>
      </section>

      <section class="section">
        <h2 class="section-title">Extracurriculars</h2>
        <ul class="list">
          <li>> Athletics (100m) and Strength Training</li>
          <li>> Design & 3D Modelling</li>
          <li>> Writing</li>
        </ul>
      </section>

      <section class="section">
        <h2 class="section-title">Educational Background</h2>
        <p>Commenced academic journey at the International School of Grenoble, followed by Bachelor's degree in Computer Science at the IUT de Paris. Professional experience encompasses both technical positions at Exteam and Econocom, and customer facing at Nike House of Innovation in Paris.</p>
        
        <div v-for="(milestone, index) in journey" :key="index" class="milestone">
          <h3 class="milestone-title">{{milestone.title}}</h3>
          <p>{{milestone.description}}</p>
        </div>
      </section>

      <section class="section">
        <h2 class="section-title">Current Research Interests</h2>
        <div v-for="(interest, index) in currentInterests" :key="index" class="interest">
          <h3 class="interest-title">{{interest.area}}</h3>
          <p>{{interest.description}}</p>
        </div>
      </section>

      <section class="section">
        <h2 class="section-title">Currently Reading/Watching</h2>
        <ul class="list">
          <li v-for="(item, index) in currentReadsWatches" :key="index">
            <span v-html="item.description"></span>
          </li>
        </ul>
      </section>

      <section class="section">
        <h2 class="section-title">Personal and University Projects</h2>
        <div v-for="(project, index) in projects" :key="index" class="project">
          <h3 class="project-title">{{ project.title }}</h3>
          <p v-html="project.description"></p>
          <template v-if="project.pdfLink">
            <a href="/Bonduelle.pdf" target="_blank" class="pdf-link">View full project here</a>
          </template>
        </div>
      </section>


      <section class="section">
        <h2 class="section-title">Contact Information</h2>
        <p>Currently seeking internship opportunities in data analysis and finance</p>
        <p class="email">E-mail: imane.benyettou@etu.u-bordeaux.fr</p>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      journey: [
        {
          title: 'Data Analysis',
          description: '> Learning advanced data analysis techniques and exploring financial technology as part of my studies'
        },
        {
          title: 'Software Design & Development',
          description: '> Contributed to the creation of an internal E-learning platform at Exteam, focusing on market research, software design, user experience, and development'
        },
        {
          title: 'Retail & Customer Service',
          description: '> Contributed to a dynamic retail environment by providing personalized service, promoting Nike products, and aligning solutions with customer expectations to uphold brand loyalty'
        }
      ],

      currentInterests: [
        {
          area: 'Data Analysis and Machine Learning',
          description: '> Exploring data science fundamentals through machine learning models, and advanced data analysis techniques for business'
        },

        {
          area: 'Mathematics & Statistics',
          description: '> Learning about mathematical modeling, statistics, and analysis methods. Currently exploring both theoretical concepts and their practical applications'
  },
        
      ],

      currentReadsWatches: [
        { description: '<a href="https://youtube.com/playlist?list=PLEDC55106E0BA18FC&si=VgPO-QhXdI72plxN" target="_blank">> Financial Theory with John Geanakoplos</a>' },
        { description: '> Zemmari, Akka, and Jenny Benois-Pineau. <i>Deep Learning in Mining of Visual Content </i> Springer, 2020' },
      ],
    
      projects: [
        {
          title: 'Economic Impact Analysis in Fashion Industry',
          description: `> Conducted comprehensive analysis examining correlations between economic cycles and fashion industry trends, identifying key market indicators. 
          <a href="https://open.substack.com/pub/imanebn/p/fashion-and-finance-how-economic?r=4qulld&utm_campaign=post&utm_medium=web" target="_blank">Read the full article here</a>`
        },
        {
          title: 'Bonduelle Group Strategic Analysis',
          description: '> Contributed to a group research project analyzing corporate growth strategies and market performance metrics, helping translate complex financial data into actionable insights.',
          pdfLink: '../assets/Bonduelle.pdf'
        },

        {
          title: 'Spark : A perfume recommendation engine',
          description: `> Designed a machine learning application that suggests perfumes based on user tweets. Users log in via Twitter, and the app analyzes their language style and preferences to provide personalized recommendations. <br><br>> Features include:<br>
  - A curated database of perfumes with detailed note compositions.<br>
  - Plans for community input to expand the perfume database.
  <br><br><a href="https://github.com/enami27/spark" target="_blank">View GitHub Repository</a>`,
        }
      ]

    }
  }
}
</script>

<style>
/* Base styles */
body {
  margin: 0;
  padding: 0;
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: #000;
  background-color: #fff;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
}

/* Header styles */
.header {
  text-align: center;
  margin-bottom: 4rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid #eee;
}

.title {
  font-size: 2.5rem;
  margin: 0 0 0.5rem;
  font-weight: 700;
}

.subtitle {
  font-size: 1.1rem;
  margin: 0 0 1rem;
  color: #444;
}

.nav {
  margin-top: 1rem;
}

.nav a {
  color: #000;
  text-decoration: none;
  padding: 0 0.5rem;
  transition: color 0.2s;
}

.nav a:hover {
  color: #666;
}

/* Section styles */
.section {
  margin-bottom: 3rem;
}

.section-title {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid #eee;
}

/* List styles */
.list {
  list-style-type: none;
  padding-left: 0;
}

.list li {
  margin-bottom: 0.5rem;
}

/* Milestone, Interest, and Project styles */
.milestone, .interest, .project {
  margin-bottom: 2rem;
}

.milestone-title, .interest-title, .project-title {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  color: #222;
}

/* Link styles */
a {
  color: #000;
  text-decoration: underline;
  text-decoration-thickness: 1px;
  text-underline-offset: 2px;
}

a:hover {
  color: #666;
}

/* Email style */
.email {
  font-family: monospace;
  background: #f5f5f5;
  padding: 0.5rem;
  display: inline-block;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .container {
    padding: 1rem;
  }
  
  .title {
    font-size: 2rem;
  }
  
  .section-title {
    font-size: 1.3rem;
  }
}

.pdf-link {
  display: inline-block;
  margin-top: 0.5rem;
  color: #0073e6;
  text-decoration: none;
}

.pdf-link:hover {
  text-decoration: underline;
  color: #005bb5;
}

</style>