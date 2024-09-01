<script>
	import Project from './Project.svelte';

	let projects = [{ name: 'OK Stuff Store', icon: 'fa-solid fa-cart-shopping' }];
</script>

<main class="flex flex-col flex-1 p-4">
	<!-- 
        1. INTRO TO PAGE
    -->
	<section id="intro" class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14">
		<div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
			<h2 class="font-light text-4xl sm:text-5xl md:text-6xl">
				Hello, I'm <span class="poppins text-violet-400">Keko</span>.
				<br />I'm a full stack web developer.
			</h2>

			<p class="text-base sm:text-lg md:text-xl">
				My <span class="text-violet-400">favourite tech</span> includes JavaScript/TypeScript, Angular,
				Node.js and, of course, Java and Python.
			</p>

			<a href="#about"
				><button
					class="mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full border-2 border-white text-white slate-950"
				>
					<div
						class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
					/>
					<h4 class="relative z-9">View my work<i class="pl-2 fas fa-arrow-down"></i></h4>
				</button></a
			>
		</div>
	</section>

	<!-- 
        2. ABOUT ME
    -->
	<section class="py-20 lg:py-32 flex flex-col gap-24" id="about">
		<div class="flex flex-col gap-2 text-center">
			<h1 class="text-3xl sm:text-4xl md:text-5xl mb-4">About me</h1>
		</div>

        <div class="flex flex-col md:flex-row space-y-4 md:space-y-0 md:space-x-4 lg:px-32">
          
            <!-- Text blurb -->
            <div class="flex-1 p-4">
              <p class="text-xl">I'm committed to lifelong learning and have hands-on experience with a diverse tech stack, 
                including <span class="text-violet-400">Angular, Spring Boot, Java, Node.js, JavaScript/TypeScript</span>, as well as <span class="text-violet-400">iOS and Android</span> app development. 
                My academic journey has equipped me with a solid foundation in building scalable and efficient web applications. 
                <br /><br />Outside of coding, I enjoy gaming and biking, which keep me inspired and balanced. I'm excited to leverage my skills and 
                enthusiasm in a professional setting as I embark on my career in web development.</p>
            </div>

            <!-- Images -->
            <div class="flex-1 p-4">
                <!-- svelte-ignore a11y-img-redundant-alt -->
                <img src={"assets/profile.png"} alt="A photo of me" class="w-auto h-auto m-auto max-h-96" />
              </div>

          </div>
	</section>

	<!-- 
        3. PROJECTS
    -->
	<section class="py-20 flex flex-col gap-24" id="projects">
		<div class="flex flex-col gap-2 text-center">
			<h1 class="text-3xl sm:text-4xl md:text-5xl">Projects</h1>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10 px-32">
			<Project project={projects[0]}>
				<p>
					OK Stuff is a Full Stack e-commerce site built in <strong class="text-violet-400"
						>Angular and Java Spring Boot</strong
					>
					with transactions powered by <strong class="text-violet-400">Stripe</strong>.
				</p>
			</Project>
		</div>
	</section>

	<!-- 
        3. CONTACT ME
    -->
	<section class="py-20 lg:py-32 flex flex-col gap-24" id="contact">
		<div class="flex flex-col gap-2 text-center">
			<h1 class="text-3xl sm:text-4xl md:text-5xl mb-4">Contact</h1>
			<p class="text-base sm:text-lg md:text-xl">
				Want to get in touch? You can email me from the form below and I'll get back to you
				as quickly as possible.
			</p>
		</div>

		<form
			action="https://formspree.io/f/xblrwnlz"
			method="POST"
			class="flex flex-col space-y-4 p-4 max-w-lg mx-auto w-full"
		>
			<div>
				<label for="name" class="poppins block text-md font-medium text-violet-400">Name</label>
				<input
					id="name"
					type="text"
					name="name"
					required
					class="text-black mt-1 block w-full px-3 py-2 border-4 rounded-md shadow-sm focus:outline-none focus:ring-violet-500 focus:border-violet-500 text-md"
				/>
			</div>

			<div>
				<label for="email" class="poppins block text-md font-medium text-violet-400">Email</label>
				<input
					id="email"
					type="email"
					name="_replyto"
					required
					class="text-black mt-1 block w-full px-3 py-2 border-4 rounded-md shadow-sm focus:outline-none focus:ring-violet-500 focus:border-violet-500 text-md"
				/>
			</div>

			<div>
				<label for="message" class="poppins block text-md font-medium text-violet-400"
					>Message</label
				>
				<textarea
					id="message"
					name="message"
					required
					class="text-black mt-1 block w-full px-3 py-2 border-4 rounded-md shadow-sm focus:outline-none focus:ring-violet-500 focus:border-violet-500 text-md"
					rows="4"
				></textarea>
			</div>

			<button
				type="submit"
				class="poppins w-full inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-lg font-medium rounded-full text-white bg-violet-600 hover:bg-violet-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-violet-500"
			>
				Submit
			</button>
		</form>
	</section>
</main>
