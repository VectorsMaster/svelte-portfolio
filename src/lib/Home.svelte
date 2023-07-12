<script>
    import myImage from '../assets/images/A.jpg'; 
    import tg from '../assets/icons/telegram.png';
    import li from '../assets/icons/linkedin.png';
    import gh    from '../assets/icons/github.png';
    import cf from '../assets/icons/codeforces.png'
</script>
<section id="home-section" class="home">
    <div class="home-content">
        <div class="profile-img">
            <!-- svelte-ignore a11y-img-redundant-alt -->
            <img src={myImage} alt="my-profile-image">
        </div>

        <h1>Hi, I'm Ahmad</h1>
        <h3>Software developer</h3>
        <p>
            I am a 2nd-year bachelor student at Innopolis University. Additionally, I am a professional competitive
            programmer and a world finalist at ICPC2022.
        </p>
        <h5 class="my-languages">Languages</h5>
        <div class="languages">
            <ul>
                <li>
                    <p>Arabic: Native Speaker.</p>
                </li>
                <li>
                    <p>English: Excellent Speaker.</p>
                </li>
                <li>
                    <p>Russian: Beginner Level.</p>
                </li>
            </ul>
        </div>
        <div id="contact-section" class="icons">
            <a id="tg-link" href="https://t.me/Ahmad_Sarhan">
                <img class="tg-icon" src={tg} alt="link-to-my-telegram">
            </a>

            <a href="https://www.linkedin.com/in/ahmad-sarhan-a9b331243/">
                <img class="li-icon" src={li} alt="link-to-my-linkedin">
            </a>

            <a id="gh-link" href="https://github.com/VectorsMaster">
                <img class="gh-icon" src={gh} alt="link-to-my-github">
            </a>

            <a id="codeforces" href="https://codeforces.com/profile/Vectors_Master">
                <img class="cf-icon" src={cf} alt="link-to-my-codeforces-account">
            </a>
        </div>
    </div>
</section>

<style>
    .home {
        height: 100vh;
        display: flex;
        align-items: center;
        padding: 0 10%;
    }

    .home-content {
        max-width: 600px;
    }

    .profile-img {
        position: inline-flex;
        margin-bottom: 10px;
        width: 100%;
    }

    .profile-img img {
        height: 250px;
        border-radius: 50%;
    }

    .home-content h1 {
        font-size: 56px;
        font-weight: 700;
    }

    .home-content h3 {
        font-size: 32px;
        font-weight: 700;
        color: rgba(240, 245, 245, 0.629);
    }

    .home-content p {
        font-size: 16px;
        margin: 20px 0 40px;
        line-height: 30px;
    }

    .home-content h5 {
        font-size: 32px;
    }

    .languages {
        margin: 13px;
    }

    .languages p {
        line-height: 5px;
        font-weight: 600;
    }

    .icons {
        display: flex;
        justify-content: space-between;
        align-items: center;
        bottom: 40px;
        width: 180px;
    }

    .icons a {
        display: inline-flex;
        position: relative;
        justify-content: center;
        align-items: center;
        width: 40px;
        height: 40px;
        background: transparent;
    }

    .icons img {
        width: 40px;
        height: 40px;
        border-radius: 50%;
    }

    .icons .cf-icon {
        border-radius: 0%;
    }
</style>