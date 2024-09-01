<script>
    let name = '';
    let email = '';
    let message = '';
  
    // This function will handle form submission
    const handleSubmit = async (event) => {
      event.preventDefault();
  
      const formData = {
        name,
        email,
        message,
      };
  
      // Example: Sending form data to a server or email service
      try {
        const response = await fetch('/send-email', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify(formData),
        });
  
        if (response.ok) {
          alert('Message sent successfully!');
          // Clear the form after successful submission
          name = '';
          email = '';
          message = '';
        } else {
          alert('There was a problem sending your message. Please try again.');
        }
      } catch (error) {
        alert('Error: ' + error.message);
      }
    };
  </script>
  
  <form on:submit={handleSubmit} class="space-y-4 p-4 max-w-md mx-auto">
    <div>
      <label for="name" class="block text-sm font-medium text-gray-700">Name</label>
      <input
        id="name"
        type="text"
        bind:value={name}
        required
        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-violet-500 focus:border-violet-500 sm:text-sm"
      />
    </div>
  
    <div>
      <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
      <input
        id="email"
        type="email"
        bind:value={email}
        required
        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-violet-500 focus:border-violet-500 sm:text-sm"
      />
    </div>
  
    <div>
      <label for="message" class="block text-sm font-medium text-gray-700">Message</label>
      <textarea
        id="message"
        bind:value={message}
        required
        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-violet-500 focus:border-violet-500 sm:text-sm"
        rows="4"
      ></textarea>
    </div>
  
    <button
      type="submit"
      class="w-full inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-violet-600 hover:bg-violet-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-violet-500"
    >
      Send Message
    </button>
  </form>