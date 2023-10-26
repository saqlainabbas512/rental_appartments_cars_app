<template>
  <div class="home-section">
    <nav class="navbar">
      <div class="left-section">
        <div class="logo">
          <img class="circular-image" src="@/assets/logo.png" alt="Country" />
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
          <img class="country" src="@/assets/country.png" alt="Country" />
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
    <div class="background-image" :style="{ backgroundImage: `url(${require('@/assets/cover8.jpg')})` }">
      <h1 class="heading">Home to Sengkang</h1>
    </div>
    <PropertyCard
      v-for="(property, index) in properties"
      :key="index"
      :title="property.title"
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
          title: "Luxury Villa with a View",
          price: "$1,500,000",
          availableDate: "2023-11-01",
          details: "Bedrooms: 4, Bathrooms: 3, Size: 2500 sqft",
          distance: "Distance from Central Point: 2 miles",
          postedBy: "John Doe",
          imageUrl: require('@/assets/apartment2.png'),
        },
        {
          title: "Cozy Apartment in the City",
          price: "$800,000",
          availableDate: "2023-11-15",
          details: "Bedrooms: 2, Bathrooms: 2, Size: 1200 sqft",
          distance: "Distance from Central Point: 1 mile",
          postedBy: "Jane Smith",
          imageUrl: require('@/assets/apartment4.png'),
        },
        {
          title: "Luxury Villa with a View",
          price: "$1,500,000",
          availableDate: "2023-11-01",
          details: "Bedrooms: 4, Bathrooms: 3, Size: 2500 sqft",
          distance: "Distance from Central Point: 2 miles",
          postedBy: "John Doe",
          imageUrl: require('@/assets/apartment5.png'),
        },
        {
          title: "Cozy Apartment in the City",
          price: "$800,000",
          availableDate: "2023-11-15",
          details: "Bedrooms: 2, Bathrooms: 2, Size: 1200 sqft",
          distance: "Distance from Central Point: 1 mile",
          postedBy: "Jane Smith",
          imageUrl: require('@/assets/appartment1.jpg'),
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
  border-radius: 50%;
  width: 50px; /* Adjust the width as needed */
  height: 50px; /* Adjust the height as needed */
  object-fit: cover;
}
.country{
  border-radius: 70%;
  width: 30px; /* Adjust the width as needed */
  height: 30px; /* Adjust the height as needed */
  object-fit: cover;
}

.profile-image{
  border-radius: 50%;
  width: 50px; /* Adjust the width as needed */
  height: 50px; /* Adjust the height as needed */
  object-fit: cover;
  margin-left: 50px;
}

.navbar {
  display: flex;
  justify-content: space-between;
  background-color: #faf7f7;
  padding-left: 300px ;
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
