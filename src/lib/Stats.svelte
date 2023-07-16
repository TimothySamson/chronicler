<script lang="ts">
    let stats: { group: string; name: string; value: string | number }[] = [
        { group: "General Info", name: "Currency", value: "$100" },
        { group: "General Info", name: "Relationships", value: "5" },  
        { group: "General Info", name: "Fame", value: "Low" },  
        { group: "General Info", name: "Infamy", value: "Low" },

        { group: "Intelligence", name: "Street Smart", value: "10" },
        { group: "Intelligence", name: "Book Smart", value: "10" },
        { group: "Intelligence", name: "Short Term Memory", value: "10" },
        { group: "Intelligence", name: "Long Term Memory", value: "10" },
        { group: "Intelligence", name: "Basic Cognition", value: "10" },

        { group: "Stats", name: "Agility", value: "10" },
        { group: "Stats", name: "Charisma", value: "8" },
        { group: "Stats", name: "Looks", value: "15" },
        { group: "Stats", name: "Flexibility", value: "35" },

        { group: "Environment", name: "Weather", value: "Sunny" },
        { group: "Environment", name: "Temperature", value: "70F" },
        { group: "Environment", name: "Atmosphere Pressure", value: "50" },
        { group: "Environment", name: "Wind Speed", value: "15 mph" },

        { group: "Setting", name: "Galaxy", value: "Milky Way" },
        { group: "Setting", name: "Planet", value: "Earth" },
        { group: "Setting", name: "Nation", value: "USA" },
        { group: "Setting", name: "Datetime", value: "2023-07-12 10:30 AM" },

        { group: "Genetics", name: "Nationality", value: "American" },
        { group: "Genetics", name: "Race", value: "Black" },
    ];
  </script>
  
  <style>
    .grid-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-gap: 20px;
    }
  
    .group {
      border: 1px solid #ccc;
      padding: 10px;
    }
  
    .group-name {
      font-weight: bold;
      margin-bottom: 5px;
      font-size: 18px;
      text-transform: uppercase;
      color: #333;
      border-bottom: 2px solid #ccc;
      padding-bottom: 5px;
    }
  
    .stat {
      margin-bottom: 10px;
    }
  
    .name {
      font-weight: bold;
    }
  
    .value {
      margin-left: 10px;
    }
  </style>
  
  <div class="grid-container">
    {#each Array.from(new Set(stats.map((stat) => stat.group))).slice(0, 3) as group}
      <div class="group">
        <div class="group-name">{group}</div>
        {#each stats.filter((stat) => stat.group === group) as stat}
          <div class="stat">
            <span class="name">{stat.name}:</span>
            <span class="value">{stat.value}</span>
          </div>
        {/each}
      </div>
    {/each}
  </div>
  <div class="grid-container">
    {#each Array.from(new Set(stats.map((stat) => stat.group))).slice(3, 6) as group}
      <div class="group">
        <div class="group-name">{group}</div>
        {#each stats.filter((stat) => stat.group === group) as stat}
          <div class="stat">
            <span class="name">{stat.name}:</span>
            <span class="value">{stat.value}</span>
          </div>
        {/each}
      </div>
    {/each}
  </div>
