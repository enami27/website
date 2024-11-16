<template>
  <div>
    <header>
      <h1>Imane Benyettou</h1>
      <p>MIAGE Student based in Bordeaux, France</p>
      <nav>
        <a href="https://substack.com/@imanebn" target="_blank">Substack</a> | 
        <a href="https://github.com/enami27" target="_blank">GitHub</a> |
        <a href="https://www.linkedin.com/in/imanebenyettou" target="_blank">Linkedin</a>
      </nav>
    </header>

    <main>
      <section>
        <h2>Professional Summary</h2>
        <p>Currently pursuing a degree in Mathematics and Computer Science (MIAGE) at the University of Bordeaux, specializing in data analysis and problem-solving methodologies. Combining technical expertise with practical business acumen.</p>
      </section>

      <section>
        <h2>Personal Development</h2>
        <ul>
          <li>Athletics and Strength Training</li>
          <li>Design and 3D Modelling</li>
          <li>Writing</li>
        </ul>
      </section>

      <section>
        <h2>Educational Background</h2>
        <p>Commenced academic journey at the International School of Grenoble, followed by Bachelor's degree in Computer Science at the IUT de. Professional experience encompasses both technical positions and retail operations at Nike House of Innovation in Paris, providing comprehensive exposure to technology and business sectors.</p>
        
        <div v-for="(milestone, index) in journey" :key="index">
          <h3>{{milestone.title}}</h3>
          <p>{{milestone.description}}</p>
        </div>
      </section>

      <section>
        <h2>Current Research Interests</h2>
        <div v-for="(interest, index) in currentInterests" :key="index">
          <h3>{{interest.area}}</h3>
          <p>{{interest.description}}</p>
        </div>
      </section>

      <section>
        <h2>Currently Reading/Watching</h2>
        <ul>
          <li v-for="(item, index) in currentReadsWatches" :key="index">
            <span v-html="item.description"></span>
          </li>
        </ul>
      </section>

      <section>
        <h2>Personal and University Projects</h2>
        <div v-for="(project, index) in projects" :key="index">
          <h3>{{project.title}}</h3>
          <p v-html="project.description"></p>
        </div>
      </section>

      <section>
        <h2>Professional Contact Information</h2>
        <p>Currently seeking internship opportunities in data analysis and finance</p>
        <p>E-mail: imane.benyettou@etu.u-bordeaux.fr</p>
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
          description: 'Learning advanced data analysis techniques and exploring financial technology as part of my studies.'
        },
        {
          title: 'Software Design & Development',
          description: 'Contributed to the creation of an internal E-learning platform at Exteam, focusing on market research, software design, user experience, and development.'
        },
        {
          title: 'Retail & Customer Service',
          description: 'Learned about customer needs and how to deliver solutions while working at Nike.'
        }
      ],

      currentInterests: [
        {
          area: 'Data Analysis and Machine Learning',
          description: 'Investigating artificial intelligence implementations for business process optimization and decision-making frameworks.'
        },
        {
          area: 'Financial Technology Systems',
          description: 'Researching the convergence of financial systems and technological innovation, with particular focus on economic pattern analysis across industry sectors.'
        },
      ],

      currentReadsWatches: [
        { description: '<a href="https://youtube.com/playlist?list=PLEDC55106E0BA18FC&si=VgPO-QhXdI72plxN" target="_blank">Financial Theory with John Geanakoplos</a>' },
        { description: 'Zemmari, Akka, and Jenny Benois-Pineau. <i>Deep Learning in Mining of Visual Content </i> Springer, 2020' },
      ],
    
      projects: [
      {
        title: 'Economic Impact Analysis in Fashion Industry',
        description: `Conducted comprehensive analysis examining correlations between economic cycles and fashion industry trends, identifying key market indicators. 
        <a href="https://open.substack.com/pub/imanebn/p/fashion-and-finance-how-economic?r=4qulld&utm_campaign=post&utm_medium=web" target="_blank">Read the full article here.</a>`
      },

        {
          title: 'Bonduelle Group Strategic Analysis',
          description: 'Contributed to a group research project analyzing corporate growth strategies and market performance metrics, helping translate complex financial data into actionable insights.'
        }
      ]
    }
  }
}
</script>