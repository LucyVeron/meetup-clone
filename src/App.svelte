<script lang="ts">
    let draft = "";
    let comments: any[] = [
        {
            poster: "Tom",
            comment: `Can't wait for the event today! 😀`,
            time: "1 day ago",
        },
    ];
    function addToCalendar(): void {
        alert("Added to calendar!");
    }
    function postComment(): void {
        const newComment: any = {
            poster: "John Doe",
            comment: draft,
            time: "Just now"
        }
        comments = [...comments, newComment];
        draft = "";
    }
</script>

<main>
    <div class="header card">
        <img src="assets/logo_mobile.png" alt="meetup" />
        <div class="header__right">
            <div class="header__right--promotion">
                <div>Start a new Group</div>
                <div>50% OFF</div>
            </div>
            <nav>
                <li><a href="https://www.google.com/">Explore</a></li>
                <li><a href="https://www.google.com/">Messages</a></li>
                <li><a href="https://www.google.com/">Notifications</a></li>
            </nav>
            <div class="profile">
                <img src="assets/tom.png" alt="profile" />
                <div class="profile__arrow">&#9660;</div>
            </div>
        </div>
    </div>
    <div class="group card">
        <img src="assets/tom.png" alt="group" />
        <div class="group__text">
            <div class="group__text--title">The Biz Club</div>
            <div class="group__text--subtitle">Public Group</div>
        </div>
    </div>
    <div class="event card">
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
    <div class="details card">
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
    <div class="comments">
        <div class="comments__title">Comments</div>
        {#each comments as comment}
            <div class="comment">
                <img src="assets/tom.png" alt="meetup" />
                <div class="col full">
                    <div class="comment__text">
                        <div class="comment__text--name">{comment.poster}</div>
                        <div class="comment__text--comment">
                            {comment.comment}
                        </div>
                    </div>
                    <div class="comment__time">{comment.time}</div>
                </div>
            </div>
        {/each}
    </div>
    <hr />
    <div class="draft">
        <img src="assets/tom.png" alt="meetup" />
        <textarea
            placeholder="Add a comment..."
            bind:value={draft}
            class="draft__box"
        />
        <div class="draft__button" on:click={postComment}>&#9658;</div>
    </div>
    <div class="footer" />
</main>

<style lang="scss">
    main {
        padding: 0;
        text-align: center;
        margin: 0 auto;
    }
    .full {
        width: 100%;
    }
    .row {
        display: flex;
    }
    .col {
        display: flex;
        flex-direction: column;
    }
    .card {
        margin: 0.5rem;
        background: white;
        border: 1px solid gainsboro;
    }
    .header {
        display: flex;
        padding: 0.5rem 1rem;
        &__right {
            display: flex;
            margin-left: auto;
            > * {
                margin: 0 0.5rem !important;
            }
            &--promotion {
                color: skyblue;
                width: 219px;
            }
        }
        nav {
            display: flex;
            align-items: center;
            justify-content: space-evenly;
            list-style-type: none;
            width: 100%;
            li {
                margin: 0 0.5rem;
                a {
                    color: grey;
                    text-decoration: none;
                }
            }
        }
        img {
            height: 40px;
        }
    }
    .profile {
        margin: auto 0;
        display: flex;
        align-items: center;
        cursor: pointer;
        img {
            border-radius: 50%;
            width: 40px;
            margin-right: 0.2rem;
        }
    }
    .group {
        display: flex;
        padding: 1rem;
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
        padding: 1rem;
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
    .comments {
        &__title {
            font-size: 20px;
            font-weight: 700;
            padding: 0 0 1rem 0.5rem;
            text-align: left;
        }
    }
    .comment {
        display: flex;
        margin-bottom: 1rem;
        &__text {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            margin: 0 0.5rem 0 1rem;
            background: white;
            padding: 1rem;
            &--name {
                font-weight: 700;
            }
        }
        &__time {
            text-align: left;
            margin-left: 1rem;
            margin-top: 0.5rem;
            color: grey;
        }
        img {
            border-radius: 50%;
            height: 40px;
            width: 40px;
        }
    }
    .draft {
        display: flex;
        align-items: center;
        padding: 1rem 0;
        > * {
            margin: 0 0.5rem;
        }
        img {
            border-radius: 50%;
            height: 35px;
            width: 40px;
        }
        &__box {
            width: 100%;
        }
        &__button {
            cursor: pointer;
        }
    }
    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
