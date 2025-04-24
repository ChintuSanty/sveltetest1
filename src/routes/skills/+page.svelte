<script lang="ts">
  type Skill = {
    label: string;
    percentage: number;
    color: string;
    startAngle: number;
    endAngle: number;
  };

  type WireFrameSkill = {
    label: string;
    percentage: number;
    color: string;
    startAngle: number;
    endAngle: number;
  };

  const radius = 100;
  const center = 125;

  export let skills: Omit<Skill, 'startAngle' | 'endAngle'>[] = [
    { label: 'React', percentage: 40, color: '#61dafb' },
    { label: 'Vue', percentage: 25, color: '#42b883' },
    { label: 'Svelte', percentage: 25, color: '#ff3e00' },
    { label: 'Angular', percentage: 10, color: '#dd0031' }
  ];

  export let wireFraming: Omit<WireFrameSkill, 'startAngle' | 'endAngle'>[] = [
    { label: 'Figma', percentage: 40, color: '#f24e1e' },
    { label: 'XD', percentage: 10, color: '#ff61a6' },
    { label: 'Sketch', percentage: 20, color: '#f7b500' },
    { label: 'Photoshop', percentage: 30, color: '#00bfff' }
  ];

  export let cloudSkills: Omit<Skill, 'startAngle' | 'endAngle'>[] = [
    { label: 'AWS', percentage: 40, color: '#ff9900' },
    { label: 'Azure', percentage: 20, color: '#0089ff' },
    { label: 'GCP', percentage: 40, color: '#f7b500' }
  ];

  export let databaseSkills: Omit<Skill, 'startAngle' | 'endAngle'>[] = [
    { label: 'MySQL', percentage: 30, color: '#00758f' },
    { label: 'MongoDB', percentage: 20, color: '#47a248' },
    { label: 'FireBase', percentage: 50, color: '#003b57' }
  ];

  export let otherSkills: Omit<Skill, 'startAngle' | 'endAngle'>[] = [
    { label: 'Bootstrap', percentage: 20, color: '#e44d26' },
    { label: 'Tailwind', percentage: 10, color: '#264de4' },
    { label: 'JavaScript', percentage: 30, color: '#f7df1e' },
    { label: 'WordPress', percentage: 20, color: '#007acc' },
    { label: 'S.E.O', percentage: 10, color: '#8cc84b' },
    { label: 'AEM UI', percentage: 10, color: '#000000' }
  ];
  // Add startAngle and endAngle to each skill
  let currentAngle = 0;
  skills = skills.map((skill) => {
    const angle = (skill.percentage / 100) * 360;
    const startAngle = currentAngle;
    const endAngle = startAngle + angle;
    currentAngle = endAngle;
    return { ...skill, startAngle, endAngle };
  });

  wireFraming = wireFraming.map((WireFrameSkill) => {
    const angle = (WireFrameSkill.percentage / 100) * 360;
    const startAngle = currentAngle;
    const endAngle = startAngle + angle;
    currentAngle = endAngle;
    return { ...WireFrameSkill, startAngle, endAngle };
  });

  cloudSkills = cloudSkills.map((skill) => {
    const angle = (skill.percentage / 100) * 360;
    const startAngle = currentAngle;
    const endAngle = startAngle + angle;
    currentAngle = endAngle;
    return { ...skill, startAngle, endAngle };
  });

  databaseSkills = databaseSkills.map((skill) => {
    const angle = (skill.percentage / 100) * 360;
    const startAngle = currentAngle;
    const endAngle = startAngle + angle;
    currentAngle = endAngle;
    return { ...skill, startAngle, endAngle };
  });

  otherSkills = otherSkills.map((skill) => {
    const angle = (skill.percentage / 100) * 360;
    const startAngle = currentAngle;
    const endAngle = startAngle + angle;
    currentAngle = endAngle;
    return { ...skill, startAngle, endAngle };
  });

  function getArcPath(startAngle: number, endAngle: number): string {
    const start = {
      x: center + radius * Math.cos((startAngle - 90) * Math.PI / 180),
      y: center + radius * Math.sin((startAngle - 90) * Math.PI / 180)
    };
    const end = {
      x: center + radius * Math.cos((endAngle - 90) * Math.PI / 180),
      y: center + radius * Math.sin((endAngle - 90) * Math.PI / 180)
    };
    const largeArc = endAngle - startAngle > 180 ? 1 : 0;

    return `M${center},${center} L${start.x},${start.y} A${radius},${radius} 0 ${largeArc},1 ${end.x},${end.y} Z`;
  }
</script>

<svelte:head>
  <title>Skills</title>
  <meta name="description" content="Technical Skills Pie Chart" />
</svelte:head>

<div class="text-column">
  <h1>Core Competencies:</h1>

  <div class="competency-buttons">
    <button>UI/UX Design & Architecture</button>
    <button>Agile Project Management</button>
    <button>Cross Functional Team Leadership</button>
    <button>Product Development & Strategy</button>
    <button>Interaction Design</button>
    <button>Usability Testing Methodologies</button>
    <button>Stakeholder Engagement</button>
    <button>Design Thinking Framework</button>
    <button>Agile Methodologies & Project Management</button>
    <button>Continuous Improvement Processes</button>
  </div>

  <h1>Technical Skills:</h1>

  <div class="pie-chart">
    <div class="inner-div">
      <h2>JS Frameworks:</h2>
      <svg viewBox="0 0 250 250" width="300" height="300">
        {#each skills as { label, color, startAngle, endAngle }}
          <path d={getArcPath(startAngle, endAngle)} fill={color} />
          <text
            x={center + radius * 0.6 * Math.cos(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            y={center + radius * 0.6 * Math.sin(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            font-size="10"
            fill="#fff"
            text-anchor="middle"
            alignment-baseline="middle"
          >
            {label}
          </text>
        {/each}
      </svg>
    </div>
    <div class="inner-div">
      <h2>WireFrame:</h2>
      <svg viewBox="0 0 250 250" width="300" height="300">
        {#each wireFraming as { label, color, startAngle, endAngle }}
          <path d={getArcPath(startAngle, endAngle)} fill={color} />
          <text
            x={center + radius * 0.6 * Math.cos(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            y={center + radius * 0.6 * Math.sin(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            font-size="10"
            fill="#fff"
            text-anchor="middle"
            alignment-baseline="middle"
          >
            {label}
          </text>
        {/each}
      </svg>
    </div>
    <div class="inner-div">
      <h2>Coud Computing:</h2>
      <svg viewBox="0 0 250 250" width="300" height="300">
        {#each cloudSkills as { label, color, startAngle, endAngle }}
          <path d={getArcPath(startAngle, endAngle)} fill={color} />
          <text
            x={center + radius * 0.6 * Math.cos(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            y={center + radius * 0.6 * Math.sin(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            font-size="10"
            fill="#fff"
            text-anchor="middle"
            alignment-baseline="middle"
          >
            {label}
          </text>
        {/each}
      </svg>
    </div>
  </div>
  <div class="pie-chart">
    <div class="inner-div">
      <h2>Database:</h2>
      <svg viewBox="0 0 250 250" width="300" height="300">
        {#each databaseSkills as { label, color, startAngle, endAngle }}
          <path d={getArcPath(startAngle, endAngle)} fill={color} />
          <text
            x={center + radius * 0.6 * Math.cos(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            y={center + radius * 0.6 * Math.sin(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            font-size="10"
            fill="#fff"
            text-anchor="middle"
            alignment-baseline="middle"
          >
            {label}
          </text>
        {/each}
      </svg>
    </div>
    <div class="inner-div">
      <h2>Others:</h2>
      <svg viewBox="0 0 250 250" width="300" height="300">
        {#each otherSkills as { label, color, startAngle, endAngle }}
          <path d={getArcPath(startAngle, endAngle)} fill={color} />
          <text
            x={center + radius * 0.6 * Math.cos(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            y={center + radius * 0.6 * Math.sin(((startAngle + endAngle) / 2 - 90) * Math.PI / 180)}
            font-size="10"
            fill="#fff"
            text-anchor="middle"
            alignment-baseline="middle"
          >
            {label}
          </text>
        {/each}
      </svg>
    </div>
  </div>
</div>

<style>
  .text-column {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
    padding: 2rem;
  }

  h1 {
    text-align: center;
  }

  .competency-buttons {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
  }

  button {
    padding: 10px 20px;
    border-radius: 25px;
    background-color: cyan;
    border: none;
    cursor: pointer;
    font-size: 0.9rem;
    font-weight: bold;
  }

  .pie-chart {
    display: flex;
    justify-content: center;
  }

  svg {
    display: block;
  }

  text {
    font-family: sans-serif;
    pointer-events: none;
  }

  .inner-div {
    flex: 1;
    padding: 20px;
    text-align: center;
  }
</style>
