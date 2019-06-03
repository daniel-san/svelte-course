<script>
  import Header from './UI/Header.svelte';
  import MeetupGrid from './Meetups/MeetupGrid.svelte';

  const meetups = [
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
</script>

<style>
  main {
    margin-top: 5rem;
  }
</style>

<Header />

<main>
  <MeetupGrid {meetups}/>
</main>