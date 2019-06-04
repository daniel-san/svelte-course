<script>
  import Header from './UI/Header.svelte';
  import MeetupGrid from './Meetups/MeetupGrid.svelte';

  let title = '';
  let subtitle = '';
  let address = '';
  let email = '';
  let description = '';
  let imageUrl = '';

  let meetups = [
    {
      id: 'm1',
      title: 'Coding Bootcamp',
      subtitle: 'Learn to code in 2 hours',
      description: 'In this meetup, we will have some experts teach you how to code in 2 hours.',
      imageUrl: 'http://flashbak.com/wp-content/uploads/2016/07/New-York-1978-1.jpg',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'code@test.com'
    },
    {
      id: 'm2',
      title: 'Swim Together',
      subtitle: 'Let\'s go for some swimming',
      description: 'We will simply swim some rounds!',
      imageUrl: 'http://clcdesign.com/wp-content/uploads/2013/06/before_and_after_new-jersey_clc_landscape_design_12.jpg',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'swim@test.com'
    },
  ];

  let addMeetup = () => { //using a arrow function for fun
    const newMeetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      description: description,
      imageUrl: imageUrl,
      contactEmail: email,
      address: address
    };

    //meetups.push(newMeetup); // DOES NOT WORK
    meetups = [
      newMeetup,
      ...meetups,
    ];
  }
</script>

<style>
  main {
    margin-top: 5rem;
  }
</style>

<Header />

<main>
  <form on:submit|preventDefault="{addMeetup}">
    <div class="form-control">
      <label for="title">Title</label>
      <input type="text" id="title" bind:value={title}>
    </div>
    <div class="form-control">
      <label for="subtitle">Subtitle</label>
      <input type="text" id="subtitle" bind:value={subtitle}>
    </div>
    <div class="form-control">
      <label for="address">Address</label>
      <input type="text" id="address" bind:value={address}>
    </div>
    <div class="form-control">
      <label for="imageUrl">Image URL</label>
      <input type="text" id="imageUrl" bind:value={imageUrl}>
    </div>
    <div class="form-control">
      <label for="email">Email</label>
      <input type="text" id="email" bind:value={email}>
    </div>
    <div class="form-control">
      <label for="description">Description</label>
      <textarea rows="3" id="description"  bind:value={description}/>
    </div>
    <button type="submit">Save</button>
  </form>
  <MeetupGrid {meetups}/>
</main>