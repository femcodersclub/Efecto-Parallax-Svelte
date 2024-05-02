<script>
  let instagramIcon = "/instagram.jpeg";
  let linkedinIcon = "/linkedin.jpeg";
  let youtubeIcon = "/youtube.jpeg";

  const femCodersLinks = {
    instagram: "https://www.instagram.com/femcoders_club/",
    linkedin: "https://www.linkedin.com/company/fem-coders-club/",
    youtube: "https://www.youtube.com/@FemcodersClub",
  };
</script>

<footer class="footer">
  <div class="container">
    <div class="row">
      <div class="col-md-4 logo-col">
        <img src="/logo.jpg" alt="femCoders Club" class="imglogo" />
      </div>
      <div class="col-md-4 text-col">
        <p>@2024 femCoders Club</p>
      </div>
      <div class="col-md-4 social-icons">
        <a href={femCodersLinks.linkedin} target="_blank"
          ><img src={linkedinIcon} alt="LinkedIn" class="social-icon" /></a
        >
        <a href={femCodersLinks.youtube} target="_blank"
          ><img src={youtubeIcon} alt="YouTube" class="social-icon" /></a
        >
        <a href={femCodersLinks.instagram} target="_blank"
          ><img src={instagramIcon} alt="Instagram" class="social-icon" /></a
        >
      </div>
    </div>
  </div>
</footer>

<style>
  .footer {
    width: 100%;
    background: linear-gradient(45deg, #e16b29, #3f3a8a, #e16b29, #3f3a8a);
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    padding: 30px 0;
    position: absolute;
    bottom: 0;
    left: 0;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
  }

  .row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
  }

  .col-md-4 {
    flex: 0 0 calc(33.333% - 20px);
    max-width: calc(33.333% - 20px);
    margin: 0 10px;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .imglogo {
    width: 80px;
    display: block;
    margin-bottom: 20px;
    border-radius: 20px;
    box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
  }
  .imglogo:hover {
    transform: scale(1.1);
  }

  .social-icon {
    width: 44px;
    height: 44px;
    transition: transform 0.3s ease;
    margin-right: 10px;
    box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
  }

  .social-icon:hover {
    transform: scale(1.1);
  }

  .text-col {
    text-align: center;
  }

  .logo-col {
    display: flex;
    justify-content: flex-start;
  }
</style>
