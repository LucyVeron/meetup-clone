<script lang="ts">
    function addToCalendar(): void {
        alert("Added to calendar!");
    }
</script>

<main>
    <div class="header">
        <img src="assets/logo_mobile.png" alt="meetup" />
    </div>
    <div class="group">
        <img src="assets/tom.png" alt="group" />
        <div class="group__text">
            <div class="group__text--title">The Biz Club</div>
            <div class="group__text--subtitle">Public Group</div>
        </div>
    </div>
    <div class="event">
        <div class="event__date">Saturday, May 15, 2021</div>
        <div class="event__title">Meet and Greet</div>
        <div class="host">
            <img src="assets/tom.png" alt="host" />
            <div class="host__text">
                <div class="host__text--title">Hosted by</div>
                <div class="host__text--subtitle">Tom</div>
            </div>
        </div>
    </div>
    <div class="details">
        <div class="details__time">
            <div class="details__time--icon">🕒</div>
            <div class="details__time--text">
                <div class="details__time--text-info">
                    <p>Saturday, May 15 2021</p>
                    <p>11:00 AM to 2:00 PM GMT+2</p>
                    <p>Every week on Saturday</p>
                </div>
                <div class="details__time--text-add" on:click={addToCalendar}>
                    Add to calendar
                </div>
            </div>
        </div>
        <div class="details__place">
            <div class="details__place--icon">📍</div>
            <div class="details__place--text">
                <div class="details__place--text-info">
                    <p>123 Sesame Street</p>
                    <p>Anytown, Germany</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer" />
</main>

<style lang="scss">
    main {
        padding: 0;
        text-align: center;
        margin: 0 auto;
    }
    .header {
        display: flex;
        padding: 0.5rem 0.3rem;
        margin: 0.5rem;
        background: white;
        border: 1px solid gainsboro;
        img {
            height: 40px;
        }
    }
    .group {
        display: flex;
        padding: 1rem;
        margin: 0.5rem;
        background: white;
        border: 1px solid gainsboro;
        &__text {
            margin: 0 1rem;
            display: flex;
            flex-direction: column;
            justify-content: space-evenly;
            &--title {
                font-weight: 700;
            }
            &--subtitle {
                font-weight: 200;
                color: grey;
            }
        }
        img {
            height: 60px;
            width: 60px;
            border-radius: 3px;
        }
    }
    .event {
        text-align: left;
        padding: 2rem 1rem;
        margin: 0.5rem;
        background: white;
        border: 1px solid gainsboro;
        &__date {
            color: grey;
        }
        &__title {
            font-weight: 800;
            font-size: 50px;
        }
    }
    .host {
        display: flex;
        &__text {
            display: flex;
            flex-direction: column;
            justify-content: space-evenly;
            margin: 0 1rem;
            &--title {
                font-weight: 200;
            }
            &--subtitle {
                font-weight: 600;
            }
        }
        img {
            height: 50px;
            width: 50px;
            border-radius: 50%;
        }
    }
    .details {
        display: flex;
        flex-direction: column;
        align-items: end;
        margin: 0.5rem;
        padding: 1rem;
        background: white;
        border: 1px solid gainsboro;
        &__time {
            display: flex;
            &--text {
                text-align: left;
                padding-left: 1rem;
                &-add {
                    color: skyblue;
                    cursor: pointer;
                }
                &-info p {
                    margin: 0;
                }
            }
        }
        &__place {
            display: flex;
            margin-top: 1rem;
            &--text {
                text-align: left;
                padding-left: 1rem;
                &-info p {
                    margin: 0;
                }
            }
        }
    }
    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
