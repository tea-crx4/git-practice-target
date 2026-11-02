<x-app-layout>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/themes/material_blue.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.19/index.global.min.css">
  
    @vite(['resources/css/jurian.css', 'resources/js/jurian.js'])
    <script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.19/index.global.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.19/locales-all.global.min.js"></script>
    <script src="https://ajaxzip3.github.io/ajaxzip3.js"></script>
    <div class="flex justify-between -mt-5 py-5">
      <h1 class="text-2xl font-medium">スケジュール一覧</h1>
    </div>
    <div class="bg-white p-4">
      <div class="flex flex-col min-[1100px]:flex-row w-full max-w-[1000px] mb-10">
        <div class="flex-1 flex items-center mt-2">
          <p>担当施術者：</p>
          <select id="healerSelect" class="h-10 max-w-[200px] min-w-[200px] rounded text-sm border border-gray-200 h-9 form-input-base form-input-normal">
            <option value="">施術者を選択</option>
             @foreach($healers as $healer)
             <option value="{{ $healer->id }}">
               {{ $healer->shijutu50_date }}
             </option>
             @endforeach
          </select>
        </div>
        <div class="flex-1 flex gap-2 mt-2">
          <button class="max-w-[200px] min-w-[200px] px-4 py-2 h-9 text-sm bg-gray-200 rounded"> 
            月間スケジュール印刷 
          </button
          ><button class="max-w-[200px] min-w-[200px] px-4 py-2 h-9 text-sm bg-gray-200 rounded"> 
            週間スケジュール印刷 
          </button>
        </div>
      </div>
     
            <div id="calendar"></div>
            
       
     
    </div>
  
</x-app-layout>
<script>
    window.calendarEvents = @json($events);
</script>

