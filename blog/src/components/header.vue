<template>
    <div class="navbar">
        <div class="logo"><span> <i class=" fa fa-h-square"></i></span>assan</div>  
      <form action="#">
          
          <input type="search" class="search-data" placeholder="Search" />
          <button type="submit" class="fa fa-search"></button>
          
        </form>

       
        
    </div>

</template>
<script>
export default {
  name: 'HEADER'
}
</script>

<style scoped>
.navbar {
    position: fixed;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: #f1dfdf;
    padding: 12px;
    color: rgb(21, 4, 99);
  }
  
  .logo {
    font-size: 30px;
    font-weight: bold;
  }
  .logo:hover{
    color: rgb(234, 0, 255);
  }

  
  .navbar form {
    display: flex;
    height: 34px;
    background: #d4c9c9;
    border-radius: 4px;
    border: 1px solid rgb(21, 4, 99);
    margin-right: 40px;
  }
  
  .navbar form .search-data {
    height: 100%;
    width: 180px;
    padding: 0 10px;
    color: rgb(21, 4, 99);
    font-weight: 500;
    background: none;
    border: none;
    font-size: 17px;
    outline: none;
    
  }
  .fa-meetup{
    color: rgb(21, 4, 99);
  }
  .navbar form button {
    background: rgb(21, 4, 99);
    border: none;
    cursor: pointer;
    font-size: 17px;
    color: #fff;
    border-radius: 2px;
    padding: 0 12px;
    
  }

  .navbar form button:hover {
    background: rgb(234, 0, 255);
  }
  @media only screen and  (max-width: 500px) {
    .navbar form {
      display: flex;
    }
  }

</style>