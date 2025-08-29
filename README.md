<html lang="en">
 <head>
  <meta charset="utf-8"/>
  <meta content="width=device-width, initial-scale=1" name="viewport"/>
  <title>
   Community Complaints &amp; Health Monitoring App
  </title>
  <script src="https://cdn.tailwindcss.com">
  </script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet"/>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&amp;display=swap" rel="stylesheet"/>
  <style>
   body {
      font-family: "Inter", sans-serif;
    }
  </style>
 </head>
 <body class="bg-gray-50 min-h-screen flex flex-col">
  <!-- Header -->
  <header class="bg-white shadow-md sticky top-0 z-40">
   <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex items-center justify-between h-16">
    <div class="flex items-center space-x-3">
     <img alt="App logo showing a stylized community icon with hands and a heart" class="h-10 w-10 rounded-full" height="80" src="https://storage.googleapis.com/a1aa/image/ec48b083-f01a-4cfd-ee5a-58ef57a17f8e.jpg" width="80"/>
     <h1 class="text-xl font-semibold text-gray-900">
      Community Complaints &amp; Health Monitoring
     </h1>
    </div>
    <nav aria-label="Primary Navigation" class="hidden md:flex space-x-6 text-gray-700 font-medium">
     <a class="hover:text-blue-600 transition" href="#complaint-form">
      Submit Complaint
     </a>
     <a class="hover:text-blue-600 transition" href="#complaints-list">
      Track Complaints
     </a>
     <a class="hover:text-blue-600 transition" href="#health-data">
      Health Data
     </a>
     <a class="hover:text-blue-600 transition" href="#analytics-dashboard">
      Analytics Dashboard
     </a>
     <a class="hover:text-blue-600 transition" href="#admin-dashboard">
      Admin Dashboard
     </a>
     <a class="hover:text-blue-600 transition" href="#education-module">
      Education
     </a>
    </nav>
    <button aria-label="Open menu" class="md:hidden text-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-blue-600" id="mobile-menu-button">
     <i class="fas fa-bars fa-lg">
     </i>
    </button>
   </div>
   <!-- Mobile menu -->
   <div class="hidden md:hidden bg-white border-t border-gray-200" id="mobile-menu">
    <a class="block px-4 py-3 text-gray-700 hover:bg-gray-100" href="#complaint-form">
     Submit Complaint
    </a>
    <a class="block px-4 py-3 text-gray-700 hover:bg-gray-100" href="#complaints-list">
     Track Complaints
    </a>
    <a class="block px-4 py-3 text-gray-700 hover:bg-gray-100" href="#health-data">
     Health Data
    </a>
    <a class="block px-4 py-3 text-gray-700 hover:bg-gray-100" href="#analytics-dashboard">
     Analytics Dashboard
    </a>
    <a class="block px-4 py-3 text-gray-700 hover:bg-gray-100" href="#admin-dashboard">
     Admin Dashboard
    </a>
    <a class="block px-4 py-3 text-gray-700 hover:bg-gray-100" href="#education-module">
     Education
    </a>
   </div>
  </header>
  <main class="flex-grow max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 space-y-20">
   <!-- Complaint Submission Form -->
   <section class="bg-white rounded-lg shadow p-6 max-w-3xl mx-auto" id="complaint-form">
    <h2 class="text-2xl font-semibold text-gray-900 mb-6">
     Submit a Complaint / Feedback
    </h2>
    <form class="space-y-6" enctype="multipart/form-data" id="complaintForm" novalidate="">
     <div>
      <label class="block text-sm font-medium text-gray-700 mb-1" for="complaintType">
       Select Type
      </label>
      <select class="block w-full rounded-md border border-gray-300 shadow-sm py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="complaintType" name="type" required="">
       <option disabled="" selected="" value="">
        Select a type
       </option>
       <option value="health">
        Health
       </option>
       <option value="water">
        Water
       </option>
       <option value="app_issue">
        App Issue
       </option>
       <option value="other">
        Other
       </option>
      </select>
     </div>
     <div>
      <label class="block text-sm font-medium text-gray-700 mb-1" for="complaintText">
       Description (Text or Voice Note)
      </label>
      <textarea class="block w-full rounded-md border border-gray-300 shadow-sm py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 resize-y" id="complaintText" name="description" placeholder="Type your complaint or feedback here..." rows="4"></textarea>
      <button class="mt-2 inline-flex items-center px-3 py-1.5 border border-red-600 text-red-600 rounded-md hover:bg-red-600 hover:text-white transition focus:outline-none focus:ring-2 focus:ring-red-600" id="recordVoiceBtn" type="button">
       <i class="fas fa-microphone mr-2">
       </i>
       Record Voice Note
      </button>
      <audio class="mt-2 hidden w-full rounded-md border border-gray-300" controls="" id="voicePlayback">
      </audio>
     </div>
     <div>
      <label class="block text-sm font-medium text-gray-700 mb-1" for="complaintMedia">
       Upload Photo or Video (optional)
      </label>
      <input accept="image/*,video/*" class="block w-full text-gray-700" id="complaintMedia" multiple="" name="media" type="file"/>
      <div class="mt-3 flex flex-wrap gap-3" id="mediaPreview">
      </div>
     </div>
     <button class="w-full bg-blue-600 text-white font-semibold py-3 rounded-md hover:bg-blue-700 transition focus:outline-none focus:ring-2 focus:ring-blue-600" type="submit">
      Submit Complaint
     </button>
    </form>
   </section>
   <!-- Complaints List (for users to track their complaints) -->
   <section class="max-w-5xl mx-auto" id="complaints-list">
    <h2 class="text-2xl font-semibold text-gray-900 mb-6">
     Track Your Complaints
    </h2>
    <div class="space-y-6">
     <article aria-label="Complaint about water quality issue near village handpump" class="bg-white rounded-lg shadow p-5 border border-gray-200" tabindex="0">
      <header class="flex justify-between items-center mb-3">
       <h3 class="text-lg font-semibold text-gray-800">
        Water quality issue near village handpump
       </h3>
       <span class="text-sm font-medium text-yellow-600 bg-yellow-100 px-2 py-0.5 rounded-full">
        Under Review
       </span>
      </header>
      <p class="text-gray-700 mb-3">
       The water tastes bad and has a strange odor. Please check the handpump near the temple.
      </p>
      <div class="flex flex-wrap gap-3 mb-3">
       <img alt="Photo showing a village handpump with a rusty pipe and water dripping" class="rounded-md max-w-[150px] h-auto object-cover" height="200" src="https://storage.googleapis.com/a1aa/image/91dfcb91-2a1d-4b76-aa05-3d8e2de2a2a1.jpg" width="300"/>
      </div>
      <footer class="text-xs text-gray-500">
       Submitted on 2024-06-01
      </footer>
     </article>
     <article aria-label="Complaint about app crashing when submitting feedback" class="bg-white rounded-lg shadow p-5 border border-gray-200" tabindex="0">
      <header class="flex justify-between items-center mb-3">
       <h3 class="text-lg font-semibold text-gray-800">
        App crashes when submitting feedback
       </h3>
       <span class="text-sm font-medium text-red-600 bg-red-100 px-2 py-0.5 rounded-full">
        Open
       </span>
      </header>
      <p class="text-gray-700 mb-3">
       The app crashes every time I try to upload a photo with my complaint.
      </p>
      <footer class="text-xs text-gray-500">
       Submitted on 2024-06-03
      </footer>
     </article>
     <article aria-label="Complaint about health worker not available in PHC" class="bg-white rounded-lg shadow p-5 border border-gray-200" tabindex="0">
      <header class="flex justify-between items-center mb-3">
       <h3 class="text-lg font-semibold text-gray-800">
        Health worker not available in PHC
       </h3>
       <span class="text-sm font-medium text-green-700 bg-green-100 px-2 py-0.5 rounded-full">
        Resolved
       </span>
      </header>
      <p class="text-gray-700 mb-3">
       The health worker was not present at the PHC last week. Please ensure availability.
      </p>
      <footer class="text-xs text-gray-500">
       Submitted on 2024-05-28
      </footer>
     </article>
    </div>
   </section>
   <!-- Health Data Collection Section -->
   <section class="bg-white rounded-lg shadow p-6 max-w-4xl mx-auto" id="health-data">
    <h2 class="text-2xl font-semibold text-gray-900 mb-6">
     Health &amp; Water Data Collection
    </h2>
    <form class="space-y-8" id="healthDataForm" novalidate="">
     <fieldset class="border border-gray-300 rounded-md p-4">
      <legend class="text-lg font-semibold text-gray-800 px-2">
       Household Registration
      </legend>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-4">
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="householdId">
         Household ID
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="householdId" name="householdId" placeholder="Enter Household ID" required="" type="text"/>
       </div>
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="householdLocation">
         Location (Geotag)
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="householdLocation" name="householdLocation" placeholder="Latitude, Longitude" required="" type="text"/>
       </div>
      </div>
     </fieldset>
     <fieldset class="border border-gray-300 rounded-md p-4">
      <legend class="text-lg font-semibold text-gray-800 px-2">
       Person Registration
      </legend>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-4">
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="personName">
         Name
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="personName" name="personName" placeholder="Enter full name" required="" type="text"/>
       </div>
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="personAge">
         Age
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="personAge" max="120" min="0" name="personAge" placeholder="Enter age" required="" type="number"/>
       </div>
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="personGender">
         Gender
        </label>
        <select class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="personGender" name="personGender" required="">
         <option disabled="" selected="" value="">
          Select gender
         </option>
         <option value="female">
          Female
         </option>
         <option value="male">
          Male
         </option>
         <option value="other">
          Other
         </option>
        </select>
       </div>
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="personRelation">
         Relation to Head
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="personRelation" name="personRelation" placeholder="E.g. Self, Spouse, Child" type="text"/>
       </div>
      </div>
     </fieldset>
     <fieldset class="border border-gray-300 rounded-md p-4">
      <legend class="text-lg font-semibold text-gray-800 px-2">
       Symptom Survey
      </legend>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-4">
       <div>
        <label class="inline-flex items-center space-x-2" for="symptomFever">
         <input class="rounded border-gray-300 text-blue-600 focus:ring-blue-500" id="symptomFever" name="symptoms" type="checkbox" value="fever"/>
         <span>
          Fever
         </span>
        </label>
       </div>
       <div>
        <label class="inline-flex items-center space-x-2" for="symptomCough">
         <input class="rounded border-gray-300 text-blue-600 focus:ring-blue-500" id="symptomCough" name="symptoms" type="checkbox" value="cough"/>
         <span>
          Cough
         </span>
        </label>
       </div>
       <div>
        <label class="inline-flex items-center space-x-2" for="symptomFatigue">
         <input class="rounded border-gray-300 text-blue-600 focus:ring-blue-500" id="symptomFatigue" name="symptoms" type="checkbox" value="fatigue"/>
         <span>
          Fatigue
         </span>
        </label>
       </div>
       <div>
        <label class="inline-flex items-center space-x-2" for="symptomOther">
         <input class="rounded border-gray-300 text-blue-600 focus:ring-blue-500" id="symptomOther" name="symptoms" type="checkbox" value="other"/>
         <span>
          Other
         </span>
        </label>
       </div>
      </div>
      <div class="mt-4">
       <label class="block text-sm font-medium text-gray-700 mb-1" for="symptomNotes">
        Additional Notes
       </label>
       <textarea class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 resize-y" id="symptomNotes" name="symptomNotes" placeholder="Describe any other symptoms or details" rows="3"></textarea>
      </div>
     </fieldset>
     <fieldset class="border border-gray-300 rounded-md p-4">
      <legend class="text-lg font-semibold text-gray-800 px-2">
       Water Test Capture
      </legend>
      <div class="mt-4">
       <label class="block text-sm font-medium text-gray-700 mb-1" for="waterTestPhoto">
        Upload Water Test Photo
       </label>
       <input accept="image/*" class="block w-full text-gray-700" id="waterTestPhoto" name="waterTestPhoto" type="file"/>
       <div class="mt-3 flex flex-wrap gap-3" id="waterTestPreview">
       </div>
      </div>
      <div class="mt-4 grid grid-cols-1 md:grid-cols-3 gap-4">
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="phLevel">
         pH Level
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="phLevel" max="14" min="0" name="phLevel" placeholder="7.0" step="0.1" type="number"/>
       </div>
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="turbidity">
         Turbidity (NTU)
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="turbidity" min="0" name="turbidity" placeholder="0.5" step="0.1" type="number"/>
       </div>
       <div>
        <label class="block text-sm font-medium text-gray-700 mb-1" for="contaminants">
         Contaminants
        </label>
        <input class="block w-full rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="contaminants" name="contaminants" placeholder="E.g. Lead, Arsenic" type="text"/>
       </div>
      </div>
     </fieldset>
     <button class="w-full bg-green-600 text-white font-semibold py-3 rounded-md hover:bg-green-700 transition focus:outline-none focus:ring-2 focus:ring-green-600" type="submit">
      Submit Health &amp; Water Data
     </button>
    </form>
   </section>
   <!-- Analytics Dashboard -->
   <section class="bg-white rounded-lg shadow p-6 max-w-7xl mx-auto" id="analytics-dashboard">
    <h2 class="text-2xl font-semibold text-gray-900 mb-6">
     Analytics Dashboard
    </h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
     <div>
      <h3 class="text-xl font-semibold text-gray-800 mb-3">
       Daily Cases Trend
      </h3>
      <canvas aria-label="Chart showing daily cases trend" id="dailyCasesChart" role="img">
      </canvas>
     </div>
     <div>
      <h3 class="text-xl font-semibold text-gray-800 mb-3">
       Water Quality Trends
      </h3>
      <canvas aria-label="Chart showing water quality trends" id="waterQualityChart" role="img">
      </canvas>
     </div>
     <div class="md:col-span-2">
      <h3 class="text-xl font-semibold text-gray-800 mb-3">
       Village Map with Risk Scores
      </h3>
      <img alt="Map showing villages color-coded by risk scores" class="w-full rounded-lg shadow-md" height="400" src="https://storage.googleapis.com/a1aa/image/17085d1a-bc51-472a-fd21-b298bc32ffc6.jpg" width="1200"/>
     </div>
    </div>
   </section>
   <!-- Admin Dashboard -->
   <section class="bg-white rounded-lg shadow p-6 max-w-7xl mx-auto" id="admin-dashboard">
    <h2 class="text-2xl font-semibold text-gray-900 mb-6">
     District Admin Dashboard
    </h2>
    <!-- Filters -->
    <form class="flex flex-col md:flex-row md:items-center md:space-x-6 mb-6 space-y-4 md:space-y-0" id="filterForm">
     <div class="flex flex-col">
      <label class="text-sm font-medium text-gray-700 mb-1" for="filterVillage">
       Filter by Village
      </label>
      <select class="rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="filterVillage" name="village">
       <option value="">
        All Villages
       </option>
       <option value="village1">
        Village 1
       </option>
       <option value="village2">
        Village 2
       </option>
       <option value="village3">
        Village 3
       </option>
      </select>
     </div>
     <div class="flex flex-col">
      <label class="text-sm font-medium text-gray-700 mb-1" for="filterType">
       Filter by Type
      </label>
      <select class="rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="filterType" name="type">
       <option value="">
        All Types
       </option>
       <option value="health">
        Health
       </option>
       <option value="water">
        Water
       </option>
       <option value="app_issue">
        App Issue
       </option>
       <option value="other">
        Other
       </option>
      </select>
     </div>
     <div class="flex flex-col">
      <label class="text-sm font-medium text-gray-700 mb-1" for="filterStatus">
       Filter by Status
      </label>
      <select class="rounded-md border border-gray-300 py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500" id="filterStatus" name="status">
       <option value="">
        All Statuses
       </option>
       <option value="open">
        Open
       </option>
       <option value="in_progress">
        In Progress
       </option>
       <option value="resolved">
        Resolved
       </option>
      </select>
     </div>
     <button class="mt-4 md:mt-0 bg-blue-600 text-white font-semibold py-2 px-6 rounded-md hover:bg-blue-700 transition focus:outline-none focus:ring-2 focus:ring-blue-600" type="submit">
      Apply Filters
     </button>
    </form>
    <!-- Complaints Table -->
    <div class="overflow-x-auto rounded-lg border border-gray-200 shadow">
     <table aria-label="Complaints Table" class="min-w-full divide-y divide-gray-200" role="table">
      <thead class="bg-gray-50">
       <tr>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         ID
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         User ID
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         Type
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         Description
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         Status
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         Created At
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         Assign To
        </th>
        <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider" scope="col">
         Update Status
        </th>
       </tr>
      </thead>
      <tbody class="bg-white divide-y divide-gray-200">
       <tr>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         101
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         villager_123
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900 capitalize">
         water
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-700 max-w-xs truncate" title="Water tastes bad near handpump at village temple.">
         Water tastes bad near handpump at village temple.
        </td>
        <td class="px-4 py-3 whitespace-nowrap">
         <span class="inline-flex px-2 text-xs font-semibold leading-5 rounded-full bg-yellow-100 text-yellow-800">
          Open
         </span>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">
         2024-06-01
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option value="">
           Unassigned
          </option>
          <option value="asha_1">
           ASHA Worker 1
          </option>
          <option value="phc_1">
           PHC Staff 1
          </option>
          <option value="asha_2">
           ASHA Worker 2
          </option>
         </select>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option selected="" value="open">
           Open
          </option>
          <option value="in_progress">
           In Progress
          </option>
          <option value="resolved">
           Resolved
          </option>
         </select>
        </td>
       </tr>
       <tr>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         102
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         asha_45
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900 capitalize">
         health
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-700 max-w-xs truncate" title="Health worker not available at PHC on 5th June.">
         Health worker not available at PHC on 5th June.
        </td>
        <td class="px-4 py-3 whitespace-nowrap">
         <span class="inline-flex px-2 text-xs font-semibold leading-5 rounded-full bg-green-100 text-green-800">
          Resolved
         </span>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">
         2024-05-28
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option selected="" value="asha_45">
           ASHA Worker 45
          </option>
          <option value="phc_1">
           PHC Staff 1
          </option>
          <option value="asha_2">
           ASHA Worker 2
          </option>
         </select>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option value="open">
           Open
          </option>
          <option value="in_progress">
           In Progress
          </option>
          <option selected="" value="resolved">
           Resolved
          </option>
         </select>
        </td>
       </tr>
       <tr>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         103
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         villager_789
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900 capitalize">
         app_issue
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-700 max-w-xs truncate" title="App crashes when uploading photo during complaint submission.">
         App crashes when uploading photo during complaint submission.
        </td>
        <td class="px-4 py-3 whitespace-nowrap">
         <span class="inline-flex px-2 text-xs font-semibold leading-5 rounded-full bg-red-100 text-red-800">
          Open
         </span>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">
         2024-06-03
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option value="">
           Unassigned
          </option>
          <option value="asha_1">
           ASHA Worker 1
          </option>
          <option value="phc_1">
           PHC Staff 1
          </option>
          <option value="asha_2">
           ASHA Worker 2
          </option>
         </select>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option selected="" value="open">
           Open
          </option>
          <option value="in_progress">
           In Progress
          </option>
          <option value="resolved">
           Resolved
          </option>
         </select>
        </td>
       </tr>
       <tr>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         104
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         asha_12
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900 capitalize">
         other
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-700 max-w-xs truncate" title="Request for additional street lights in village center.">
         Request for additional street lights in village center.
        </td>
        <td class="px-4 py-3 whitespace-nowrap">
         <span class="inline-flex px-2 text-xs font-semibold leading-5 rounded-full bg-yellow-100 text-yellow-800">
          In Progress
         </span>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">
         2024-06-02
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option selected="" value="asha_12">
           ASHA Worker 12
          </option>
          <option value="phc_1">
           PHC Staff 1
          </option>
          <option value="asha_2">
           ASHA Worker 2
          </option>
         </select>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option value="open">
           Open
          </option>
          <option selected="" value="in_progress">
           In Progress
          </option>
          <option value="resolved">
           Resolved
          </option>
         </select>
        </td>
       </tr>
       <tr>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         105
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         villager_456
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900 capitalize">
         water
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-700 max-w-xs truncate" title="Handpump leaking water continuously near school.">
         Handpump leaking water continuously near school.
        </td>
        <td class="px-4 py-3 whitespace-nowrap">
         <span class="inline-flex px-2 text-xs font-semibold leading-5 rounded-full bg-yellow-100 text-yellow-800">
          Open
         </span>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">
         2024-06-04
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option value="">
           Unassigned
          </option>
          <option value="asha_1">
           ASHA Worker 1
          </option>
          <option value="phc_1">
           PHC Staff 1
          </option>
          <option value="asha_2">
           ASHA Worker 2
          </option>
         </select>
        </td>
        <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">
         <select class="rounded-md border border-gray-300 py-1 px-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500">
          <option selected="" value="open">
           Open
          </option>
          <option value="in_progress">
           In Progress
          </option>
          <option value="resolved">
           Resolved
          </option>
         </select>
        </td>
       </tr>
      </tbody>
     </table>
    </div>
    <!-- Map View -->
    <div class="mt-10">
     <h3 class="text-xl font-semibold text-gray-900 mb-4">
      Map View of Complaints
     </h3>
     <img alt="Map view showing a district map with multiple complaint pins marked at various village locations" class="w-full rounded-lg shadow-md" height="400" src="https://storage.googleapis.com/a1aa/image/b134025f-3256-458a-699b-03dad67ee35d.jpg" width="1200"/>
    </div>
    <!-- Export Reports -->
    <div class="mt-8 flex justify-end space-x-4">
     <button class="inline-flex items-center bg-green-600 text-white font-semibold py-2 px-5 rounded-md hover:bg-green-700 transition focus:outline-none focus:ring-2 focus:ring-green-600" type="button">
      <i class="fas fa-file-export mr-2">
      </i>
      Export Reports (CSV)
     </button>
     <button class="inline-flex items-center bg-indigo-600 text-white font-semibold py-2 px-5 rounded-md hover:bg-indigo-700 transition focus:outline-none focus:ring-2 focus:ring-indigo-600" type="button">
      <i class="fas fa-file-pdf mr-2">
      </i>
      Export Reports (PDF)
     </button>
    </div>
   </section>
   <!-- Education Module -->
   <section class="bg-white rounded-lg shadow p-6 max-w-4xl mx-auto" id="education-module">
    <h2 class="text-2xl font-semibold text-gray-900 mb-6">
     Education Module
    </h2>
    <p class="mb-4 text-gray-700">
     Access audio and text educational content in multiple local languages to raise awareness about health, water safety, and app usage.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
     <article class="bg-gray-100 rounded-lg p-4 flex flex-col items-center">
      <img alt="Illustration of a woman listening to audio content on a smartphone" class="w-full h-40 object-cover rounded-md mb-4" height="160" src="https://storage.googleapis.com/a1aa/image/81fb8483-4b74-4538-e757-311179828813.jpg" width="320"/>
      <h3 class="font-semibold text-lg mb-2">
       Audio Lessons
      </h3>
      <button class="inline-flex items-center bg-blue-600 text-white px-4 py-2 rounded-md hover:bg-blue-700 transition focus:outline-none focus:ring-2 focus:ring-blue-600" type="button">
       <i class="fas fa-play mr-2">
       </i>
       Play Audio
      </button>
     </article>
     <article class="bg-gray-100 rounded-lg p-4 flex flex-col items-center">
      <img alt="Illustration of a book with text content in multiple languages" class="w-full h-40 object-cover rounded-md mb-4" height="160" src="https://storage.googleapis.com/a1aa/image/83fa0f9a-eed6-4534-6677-3182d0620ff7.jpg" width="320"/>
      <h3 class="font-semibold text-lg mb-2">
       Text Lessons
      </h3>
      <button class="inline-flex items-center bg-blue-600 text-white px-4 py-2 rounded-md hover:bg-blue-700 transition focus:outline-none focus:ring-2 focus:ring-blue-600" type="button">
       <i class="fas fa-book mr-2">
       </i>
       Read Content
      </button>
     </article>
     <article class="bg-gray-100 rounded-lg p-4 flex flex-col items-center">
      <img alt="Illustration of a smartphone with multi-language options" class="w-full h-40 object-cover rounded-md mb-4" height="160" src="https://storage.googleapis.com/a1aa/image/69ee7e44-4293-4c43-8ade-c4682bc2321b.jpg" width="320"/>
      <h3 class="font-semibold text-lg mb-2">
       Multi-language Support
      </h3>
      <p class="text-center text-gray-600">
       Switch between local languages easily for better understanding.
      </p>
     </article>
    </div>
   </section>
  </main>
  <footer class="bg-white border-t border-gray-200 py-6 mt-auto">
   <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-gray-500 text-sm">
    © 2024 Community Complaints &amp; Health Monitoring App. All rights reserved.
   </div>
  </footer>
  <script src="https://cdn.jsdelivr.net/npm/chart.js">
  </script>
  <script>
   // Mobile menu toggle
    const mobileMenuBtn = document.getElementById("mobile-menu-button");
    const mobileMenu = document.getElementById("mobile-menu");
    mobileMenuBtn.addEventListener("click", () => {
      mobileMenu.classList.toggle("hidden");
    });

    // Voice recording logic
    const recordBtn = document.getElementById("recordVoiceBtn");
    const complaintText = document.getElementById("complaintText");
    const voicePlayback = document.getElementById("voicePlayback");
    let mediaRecorder;
    let audioChunks = [];

    recordBtn.addEventListener("click", async () => {
      if (recordBtn.dataset.recording === "true") {
        // Stop recording
        mediaRecorder.stop();
        recordBtn.dataset.recording = "false";
        recordBtn.innerHTML = '<i class="fas fa-microphone mr-2"></i> Record Voice Note';
      } else {
        // Start recording
        if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
          alert("Your browser does not support audio recording.");
          return;
        }
        try {
          const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
          mediaRecorder = new MediaRecorder(stream);
          audioChunks = [];
          mediaRecorder.addEventListener("dataavailable", (event) => {
            audioChunks.push(event.data);
          });
          mediaRecorder.addEventListener("stop", () => {
            const audioBlob = new Blob(audioChunks, { type: "audio/webm" });
            const audioUrl = URL.createObjectURL(audioBlob);
            voicePlayback.src = audioUrl;
            voicePlayback.classList.remove("hidden");

            // Simulate voice-to-text conversion (for demo)
            complaintText.value = "Voice note recorded. (Transcription not implemented)";
          });
          mediaRecorder.start();
          recordBtn.dataset.recording = "true";
          recordBtn.innerHTML = '<i class="fas fa-stop mr-2"></i> Stop Recording';
        } catch (err) {
          alert("Could not start audio recording: " + err.message);
        }
      }
    });

    // Media preview for uploaded files (complaint form)
    const complaintMedia = document.getElementById("complaintMedia");
    const mediaPreview = document.getElementById("mediaPreview");

    complaintMedia.addEventListener("change", () => {
      mediaPreview.innerHTML = "";
      const files = complaintMedia.files;
      if (!files.length) return;

      Array.from(files).forEach((file) => {
        const fileType = file.type;
        const reader = new FileReader();

        reader.onload = (e) => {
          if (fileType.startsWith("image/")) {
            const img = document.createElement("img");
            img.src = e.target.result;
            img.alt = `Uploaded image preview: ${file.name}`;
            img.className = "rounded-md max-w-[150px] h-auto object-cover";
            mediaPreview.appendChild(img);
          } else if (fileType.startsWith("video/")) {
            const video = document.createElement("video");
            video.src = e.target.result;
            video.controls = true;
            video.className = "rounded-md max-w-[150px] h-auto object-cover";
            mediaPreview.appendChild(video);
          }
        };

        reader.readAsDataURL(file);
      });
    });

    // Media preview for water test photo
    const waterTestPhoto = document.getElementById("waterTestPhoto");
    const waterTestPreview = document.getElementById("waterTestPreview");

    waterTestPhoto.addEventListener("change", () => {
      waterTestPreview.innerHTML = "";
      const files = waterTestPhoto.files;
      if (!files.length) return;

      Array.from(files).forEach((file) => {
        const fileType = file.type;
        const reader = new FileReader();

        reader.onload = (e) => {
          if (fileType.startsWith("image/")) {
            const img = document.createElement("img");
            img.src = e.target.result;
            img.alt = `Water test photo preview: ${file.name}`;
            img.className = "rounded-md max-w-[150px] h-auto object-cover";
            waterTestPreview.appendChild(img);
          }
        };

        reader.readAsDataURL(file);
      });
    });

    // Complaint form submission (demo only)
    const complaintForm = document.getElementById("complaintForm");
    complaintForm.addEventListener("submit", (e) => {
      e.preventDefault();
      const type = complaintForm.type.value;
      const description = complaintForm.description.value.trim();

      if (!type) {
        alert("Please select a complaint type.");
        return;
      }
      if (!description) {
        alert("Please enter a description or record a voice note.");
        return;
      }

      alert("Complaint submitted successfully! (Demo only, no backend integration)");
      complaintForm.reset();
      mediaPreview.innerHTML = "";
      voicePlayback.src = "";
      voicePlayback.classList.add("hidden");
    });

    // Health data form submission (demo only)
    const healthDataForm = document.getElementById("healthDataForm");
    healthDataForm.addEventListener("submit", (e) => {
      e.preventDefault();
      // Basic validation example
      if (!healthDataForm.householdId.value.trim()) {
        alert("Please enter Household ID.");
        return;
      }
      if (!healthDataForm.householdLocation.value.trim()) {
        alert("Please enter Household Location.");
        return;
      }
      if (!healthDataForm.personName.value.trim()) {
        alert("Please enter Person Name.");
        return;
      }
      if (!healthDataForm.personAge.value.trim()) {
        alert("Please enter Person Age.");
        return;
      }
      if (!healthDataForm.personGender.value) {
        alert("Please select Person Gender.");
        return;
      }

      alert("Health & Water data submitted successfully! (Demo only, no backend integration)");
      healthDataForm.reset();
      waterTestPreview.innerHTML = "";
    });

    // Filter form submission (demo only)
    const filterForm = document.getElementById("filterForm");
    filterForm.addEventListener("submit", (e) => {
      e.preventDefault();
      alert("Filters applied! (Demo only, no backend integration)");
    });

    // Chart.js charts for analytics dashboard
    const dailyCasesCtx = document.getElementById("dailyCasesChart").getContext("2d");
    const waterQualityCtx = document.getElementById("waterQualityChart").getContext("2d");

    const dailyCasesChart = new Chart(dailyCasesCtx, {
      type: "line",
      data: {
        labels: [
          "2024-05-25",
          "2024-05-26",
          "2024-05-27",
          "2024-05-28",
          "2024-05-29",
          "2024-05-30",
          "2024-05-31",
          "2024-06-01",
          "2024-06-02",
          "2024-06-03",
          "2024-06-04",
        ],
        datasets: [
          {
            label: "Daily Cases",
            data: [5, 7, 6, 8, 10, 9, 12, 15, 14, 13, 11],
            borderColor: "#2563EB",
            backgroundColor: "rgba(37, 99, 235, 0.3)",
            fill: true,
            tension: 0.3,
            pointRadius: 4,
            pointHoverRadius: 6,
          },
        ],
      },
      options: {
        responsive: true,
        plugins: {
          legend: { display: true },
          tooltip: { mode: "index", intersect: false },
        },
        scales: {
          x: {
            display: true,
            title: { display: true, text: "Date" },
          },
          y: {
            display: true,
            title: { display: true, text: "Number of Cases" },
            beginAtZero: true,
          },
        },
      },
    });

    const waterQualityChart = new Chart(waterQualityCtx, {
      type: "bar",
      data: {
        labels: ["Village 1", "Village 2", "Village 3", "Village 4", "Village 5"],
        datasets: [
          {
            label: "Average pH Level",
            data: [6.8, 7.2, 6.5, 7.0, 6.9],
            backgroundColor: "#10B981",
          },
          {
            label: "Average Turbidity (NTU)",
            data: [1.2, 0.8, 1.5, 1.0, 1.3],
            backgroundColor: "#F59E0B",
          },
        ],
      },
      options: {
        responsive: true,
        plugins: {
          legend: { position: "top" },
          tooltip: { mode: "index", intersect: false },
        },
        scales: {
          x: {
            stacked: true,
            title: { display: true, text: "Village" },
          },
          y: {
            stacked: false,
            title: { display: true, text: "Value" },
            beginAtZero: true,
          },
        },
      },
    });
  </script>
 </body>
</html>
