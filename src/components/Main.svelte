<script>
    import Step from "./Step.svelte";

    let steps = [
        {
            name: "Smoljames Store",
            icon: "fa-solid fa-cart-shopping",
            description:
                "Smoljames Store is a a merchanising store created with Next.js, Commerce.js & Stripe! Commerce.js is a CMS for managing project and Stripe is used for all transaction handling.",
        },
        {
            name: "Utlimate Todos",
            icon: "fa-solid fa-list-check",
            description:
                "Test for model robustness with customized test profiles and receive exhaustive reporting on the performance and potential vulnerabilities of your model.",
        },
        {
            name: "Pokédex",
            icon: "fa-solid fa-diagram-project",
            description:
                "Augment your datasets with our filters and dataset manipulations to ensure your models are trained on the highest quality datasets (coming soon).",
        },
    ];

    let benefits = [
        {
            metric: "10x",
            name: "a self taught developer",
            description:
                "I taught myself to code using free online resources and absolutely fell in love with the creativity and problem solving that is involved in developing and engineering innovative new online experiences. Starting of with JavaScript, HTML & CSS and evolving my knowledge base to include JavaScript frameworks, backend programming, design, cloud services and much much more.",
        },
        {
            name: "a product design & UX finatic",
            description:
                "Carefully crafting and designing amazing user experiences allows me to express and experiment with every morsel of creativity I have. I love the challenge of learning new design concepts and enabling users with amazing online experiences.",
        },
        {
            name: "an excellent communicator",
            description:
                "Communication is key and it's a paramount value of mine. I believe in transparency and constructive communication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.",
        },
    ];
</script>

<style>
    .profile-circle {
        position: relative;
        width: 350px; /* increased the size */
        height: 350px; /* increased the size */
        border-radius: 50%;
        overflow: hidden;
        margin: 0 auto;
        transition: transform 0.3s ease-in-out;
        background-color: #ffffff; /* add this line */
    }

    .profile-circle img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 50%;
    }

    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: transparent; /* update this line */
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .overlay::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        transform: scale(0);
        transition: transform 0.3s ease-in-out;
    }

    .profile-circle:hover {
        transform: scale(1.2);
    }

    .profile-circle:hover .overlay::before {
        transform: scale(1);
    }
</style>

<main class="bg-white text-black flex flex-col flex-1 p-4">
    <section
        id="introPage"
        class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
    >
        <div
            class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
        >
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span class="poppins text-black">Romar</span> Longos
                <br />BSCS 
                <span class="poppins text-black">Student</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                My <span class="text-black"> favorite tech</span> Python
            </p>
            <button
                class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950"
                style="margin-top: 20px;"
            >
                <div
                    class ="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class ="relative z-9 ">Get in touch &rarr;</h4>
            </button>
        </div>
        <div class="profile-circle bg-white">
            <img src={"images/1.jpg"} alt="Profile Picture" />
            <div class="overlay"></div>
        </div>
    </section>
    <section class="py-20 lg:py-32 flex flex-col gap-24" id="projects">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-large sm:text-xl md:text-2xl">
                A few of my creative endeavors.
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Curious to <span class="poppins text-violet-400">see</span> my work?
            </h3>
        </div>
        <a
            href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
            target="_blank"
            class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <i class="fa-regular fa-circle-play" />
            <p>Watch the video</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            <Step step={steps[0]}>
                <p>
                    Smoljames Store is a a merchanising store created with <strong
                        class="text-violet-400"
                        >Next.js, Commerce.js, Stripe & Node.js + Express.js!</strong
                    > Commerce.js is a product CMS and Stripe is used for all transaction
                    handling.
                </p>
            </Step>
            <Step step={steps[1]}>
                <p>
                    Ultimate Todos is a Full Stack <strong
                        class="text-violet-400">Next.js</strong
                    >,
                    <strong class="text-violet-400">Node.js + Express.js</strong
                    >
                    & <strong class="text-violet-400">Firebase</strong> CRUD application
                    that allows a user to login, manage a tidy and efficacious todo
                    list, and persist this information across devices.
                </p>
            </Step>
            <Step step={steps[2]}>
                <p>
                    The Pokédex is a <strong class="text-violet-400"
                        >SvelteKit & TailwindCSS</strong
                    >
                    web application, hosted on
                    <strong class="text-violet-400">Netlify</strong>, that
                    consumes and caches the
                    <strong class="text-violet-400">Pokémon API</strong>
                    to display all Pokémon information. Gotta catch them all!
                </p>
            </Step>
        </div>
    </section>
    <section id="about" class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
        <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-gray-200 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-gray-200 py-4">
            <h6 class="text-large sm:text-xl md:text-2xl">Want to know more?</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">A bit about me.</h3>
        </div>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
            <div class="flex flex-col gap-6">
                <h4 class="text-2xl sm:text-3xl md:text-4xl font-semibold">My Interests</h4>
                <div class="flex flex-wrap gap-4 justify-center">
                    <div class="bg-gray-200 p-4 rounded-md">
                        <i class="fa-solid fa-code text-2xl sm:text-3xl md:text-4xl"></i>
                        <p class="text-lg sm:text-xl md:text-2xl">Coding</p>
                    </div>
                    <div class="bg-gray-200 p-4 rounded-md">
                        <i class="fa-solid fa-palette text-2xl sm:text-3xl md:text-4xl"></i>
                        <p class="text-lg sm:text-xl md:text-2xl">Design</p>
                    </div>
                    <div class="bg-gray-200 p-4 rounded-md">
                        <i class="fa-solid fa-book text-2xl sm:text-3xl md:text-4xl"></i>
                        <p class="text-lg sm:text-xl md:text-2xl">Reading</p>
                    </div>
                </div>
            </div>
            <div class="flex flex-col gap-6">
                <h4 class="text-2xl sm:text-3xl md:text-4xl font-semibold">My Skills</h4>
                <div class="flex flex-wrap gap-4 justify-center">
                    <div class="bg-gray-200 p-4 rounded-md">
                        <i class="fa-solid fa-laptop text-2xl sm:text-3xl md:text-4xl"></i>
                        <p class="text-lg sm:text-xl md:text-2xl">Web Development</p>
                    </div>
                    <div class="bg-gray-200 p-4 rounded-md">
                        <i class="fa-solid fa-mobile-alt text-2xl sm:text-3xl md:text-4xl"></i>
                        <p class="text-lg sm:text-xl md:text-2xl">Mobile App Development</p>
                    </div>
                    <div class="bg-gray-200 p-4 rounded-md">
                        <i class="fa-solid fa-camera text-2xl sm:text-3xl md:text-4xl"></i>
                        <p class="text-lg sm:text-xl md:text-2xl">Photography</p>
                    </div>
                </div>
            </div>
        </div>
        <h5 class="text-2xl sm:text-3xl font-semibold text-center">The Complete Package</h5>
        <div class="flex flex-col overflow-x-scroll gap-10 max-w-[800px] mx-auto w-full">
            <table class="bg-white text-slate-700 rounded text-center">
                <thead class="border-b border-solid border-slate-200">
                    <tr class="">
                        <th />
                        <th class="whitespace-nowrap p-2 px-4">Candidate #1</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate #2</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate #3</th>
                        <th class="bg-gray-200 text-black whitespace-nowrap p-4 px-8">Me</th>
                    </tr>
                </thead>
                <tbody>
                    <tr class="border-b border-solid border-slate-200">
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm text-center">Dedication</td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-b border-solid border-slate-200">
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm text-center">Critical Thought</td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr>
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm text-center">Interpersonal Skills</td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-t border-solid border-slate-200">
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm text-center">Programming Ability</td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="mx-auto -mt-12 italic sm:hidden opacity-50">
            <p>Scroll to see more &rarr;</p>
        </div>
        <p class="mx-auto">So why not invest?</p>
    </section>

    
</main>