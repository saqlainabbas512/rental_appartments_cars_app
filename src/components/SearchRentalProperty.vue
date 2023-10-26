<template>
  <div class="home-section">
    <nav class="navbar">
      <div class="left-section">
        <div class="logo">
          <img class="circular-image" src="@/assets/logo1.png" alt="Country" />
        </div>
        <div class="nav-item" @mouseover="hoverNavItem = 0" @mouseleave="hoverNavItem = -1">
          <i class="fas fa-compass action-icon" v-if="hoverNavItem === 0"></i>
          Explore
        </div>
        <div class="nav-item" @mouseover="hoverNavItem = 1" @mouseleave="hoverNavItem = -1">
          <i class="fas fa-home action-icon" v-if="hoverNavItem === 1"></i>
          My Resale Properties
        </div>
        <div class="nav-item" @mouseover="hoverNavItem = 2" @mouseleave="hoverNavItem = -1">
          <i class="fas fa-cogs action-icon" v-if="hoverNavItem === 2"></i>
          Manage Properties
        </div>
        <div class="nav-item" @mouseover="hoverNavItem = 3" @mouseleave="hoverNavItem = -1">
          <i class="fas fa-calendar action-icon" v-if="hoverNavItem === 3"></i>
          Date Filter
        </div>
        <div class="logo">
          <img class="country" src="@/assets/singapore.png" alt="Country" />
        </div>
      </div>
      <div class="right-section">
        <div class="logo">
          <img class="action-button" src="@/assets/action.png" alt="Menu" />
          <img class="profile-image" src="@/assets/profileP.png" alt="Profile" />
        </div>
      </div>
    </nav>
    <div class="content-container">
      <div class="search-bars">
        <input type="text" placeholder="Country" class="search-input" />
        <input type="text" placeholder="City" class="search-input" />
        <input type="text" placeholder="Area" class="search-input" />
        <input type="date" class="search-input" />
        <button class="search-button">Search</button>
      </div>
    </div>
    <div class="background-image" :style="{ backgroundImage: `url(${require('@/assets/cover6.png')})` }">
      <h1 class="heading">Home to Sengkang</h1>
    </div>
    <PropertyCard
      v-for="(property, index) in properties"
      :key="index"
      :title="property.title"
      :subTitle="property.subTitle"
      :price="property.price"
      :availableDate="property.availableDate"
      :details="property.details"
      :distance="property.distance"
      :postedBy="property.postedBy"
      :imageUrl="property.imageUrl"
    />
  </div>
</template>

<script>
import PropertyCard from "@/components/PropertyCard.vue";

export default {
  name: "SearchRentalProperty",
  components: {
    PropertyCard,
  },
  data() {
    return {
      properties: [
        {
          title: "RiverTree's Residence",
          subTitle: "23 Elmo's Road",
          price: "$S 4,800,000",
          availableDate: "Available from 28 June 2023",
          details: "2 Bedrooms, Bathroom, 612 sqft",
          distance: "3.2 kms from Exit B of Sengang MRT",
          postedBy: "Ethan L.",
          imageUrl: require('@/assets/first.jpeg'),
        },
        {
          title: "Greenvale Town",
          subTitle: "Rose Strept 805",
          price: "S$ 5.200.000",
          availableDate: "Available",
          details: "3 Bedrooms, 2 Bathroom, 789 sgft",
          distance: "43 kms from Exit A of Sengkang MRT",
          postedBy: "Jessie H",
          imageUrl: require('@/assets/second.jpeg'),
        },
        {
          title: "RiverTree's Residence",
          subTitle: "23 Elmo's Road",
          price: "$S 4,800,000",
          availableDate: "Available from 28 June 2023",
          details: "2 Bedrooms, Bathroom, 612 sqft",
          distance: "3.2 kms from Exit B of Sengang MRT",
          postedBy: "Ethan L.",
          imageUrl: require('@/assets/first.jpeg'),
        },
        {
          title: "Greenvale Town",
          subTitle: "Rose Strept 805",
          price: "S$ 5.200.000",
          availableDate: "Available",
          details: "3 Bedrooms, 2 Bathroom, 789 sgft",
          distance: "43 kms from Exit A of Sengkang MRT",
          postedBy: "Jessie H",
          imageUrl: require('@/assets/second.jpeg'),
        },
      ],
    };
  },
};
</script>

<style scoped>
.home-section {
  text-align: center;
}

.background-image {
  width: 100%;
  height: 400px;
  object-fit: fill;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.content-container {
  padding: 0px 0 0 0;
}

.circular-image {
  border-radius: 10%;
  width: 120px; 
  height: 70px;
  object-fit: cover;
}
.country{
  border-radius: 70%;
  width: 30px; 
  height: 30px;
  object-fit: cover;
}

.profile-image{
  border-radius: 50%;
  width: 50px; 
  height: 50px;
  object-fit: cover;
  margin-left: 50px;
}

.navbar {
  display: flex;
  justify-content: space-between;
  background-color: #faf7f7;
  padding-left: 30%;
}

.nav-item {
  margin: 0 10px;
  cursor: pointer;
  display: flex;
  align-items: center;
}

.nav-item:hover {
  background-color: #569ce7;
  color: #fff;
}

.nav-item i {
  margin-right: 5px;
  display: none;
}

.nav-item:hover i {
  display: inline;
}

.right-section{
  display: flex;
  width: 300px;
  padding: 10px;
  align-items: flex-end;
  background-color: #03356a;
}

.left-section{
  display: flex;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
}

.action-button {
  background-color: #f6f8f9;
}

.action-icon {
  margin-right: 5px;
  font-size: 20px;
}

.search-bars {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(190, 247, 152, 0.7);
  padding: 10px;
}

.search-input {
  padding: 10px;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  width: 200px;
}

.search-button {
  padding: 10px 20px;
  background-color: #007BFF;
  color: #fff;
  border: none;
  border-radius: 5px;
  font-size: 16px;
}

.heading {
  position: absolute;
  top: 60%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-family: Arial, Helvetica, sans-serif;
  font-size: 45px;
  color: rgb(251, 247, 247);
}
</style>
