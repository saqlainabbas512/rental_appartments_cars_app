<template>
  <div class="home-section">
    <nav class="navbar">
      <div class="nav-item">Explore</div>
      <div class="nav-item">My Resale Properties</div>
      <div class="nav-item">Manage Properties</div>
      <div class="nav-item">Date Filter</div>
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
    <div class="background-image" :style="{ backgroundImage: `url(${require('@/assets/cover.png')})` }">
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
  padding: 20px;
}

.background-image {
  width: 100%;
  height: 400px;
  object-fit: cover;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.content-container {
  padding: 0px 0 0 0;
}

.profile {
  width: 10%;
  height: 100%;
  background-color: #007BFF;
  justify-content: flex-end;
  display: flex;
  padding: 10px;
}

.navbar {
  display: flex;
  justify-content: center;
  background-color: #ddd7d7;
  padding: 10px;
}

.nav-item {
  margin: 0 10px;
}

.search-bars {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(210, 246, 186, 0.7);
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
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 24px;
  color: white;
}

.action-button {
  background-color: blue;
  color: #fff;
  padding: 10px;
  border: none;
  border-radius: 5px;
  font-size: 20px;
  margin-left: 10px;
}

.action-icon {
  font-size: 20px;
}
</style>
