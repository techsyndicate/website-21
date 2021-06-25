<script>
  import Jumbotron from "../components/Jumbotron.svelte";
  import MemberCard from "../components/MemberCard.svelte";
  import SearchBar from "../components/SearchBar.svelte";
  import members from "../../data/members.json";

  let membersToInflate = members;

  const handleMessage = (event) => {
    if (event.detail.text === false) {
      membersToInflate = members;
      membersToInflate = membersToInflate;
    } else {
      membersToInflate = updateMembers(event.detail.text);
    }
  };

  const membersIntoRows = (members) => {
    let finalArray = [];
    const ranges = [
      [0, 3],
      [4, 7],
      [8, 11],
      [12, 15],
      [16, 19],
      [20, 23],
    ];
    ranges.forEach((range) => {
      let row = [];
      try {
        for (let i = range[0]; i < range[1] + 1; i++) {
          row.push(members[i]);
        }
      } catch (error) {}
      finalArray.push(row);
    });
    return finalArray;
  };

  const updateMembers = (q) => {
    try {
      const updatedMembers = [];
      members.forEach((rows) => {
        rows.forEach((m) => {
          const includesName = m.name
            .trim()
            .toLowerCase()
            .includes(q.trim().toLowerCase());
          if (includesName) {
            updatedMembers.push(m);
          }
        });
      });
      return membersIntoRows(updatedMembers);
    } catch (error) {
      return false;
    }
  };
</script>

<svelte:head>
  <title>TS | Members</title>
</svelte:head>

<body>
  <Jumbotron
    title="Members"
    description="Tech Syndicate's team comprises of members with a wide array of skills ranging all the way from hardware and quiz to web development and design, all united by the passion and enthusiasm for tech."
  />
  <div style="height: 3vh" />
  <SearchBar on:message={handleMessage} />
  <div style="height: 7vh" />

  {#each membersToInflate as rows}
    <div class="container">
      {#each rows as member}
        {#if member !== undefined}
          <MemberCard
            member={member.name}
            role={member.role}
            image={member.image}
            socials={member.socials}
          />
        {/if}
      {/each}
    </div>
    <div class="sized-box" />
  {/each}

  <div style="height: 12vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }

  .container {
    display: flex;
    justify-content: left;
  }

  .sized-box {
    height: 4vh;
  }

  @media screen and (max-width: 768px) {
    body {
      padding: 0 8%;
    }

    .container {
      display: block;
      justify-content: center;
    }

    .sized-box {
      height: 0;
    }
  }
</style>
