<script>
  let {data} = $props();
  let memo = $state('');


$effect(() => {
  if(data.slug ==='memo') {
    const saved = localStorage.getItem('memo');
    if(saved) memo = saved; 
  }
});

function save() {
  localStorage.setItem('memo', memo);
  alert('저장 완료!');
}
</script>

<h2>{data.item.title}</h2>
<p>{data.item.body}</p>

{#if data.slug === 'memo'}
<textarea rows = "6" bind:value={memo} class="card"  style="width:100%"></textarea>
<button onclick ={save}> 메모 저장 </button>
<p style="opacity:.6">브라우저 로컬에 저장됩니다 </p>
{:else if data.slug === 'timetable'}
<p>시간표는 아직 준비중입니다 ㅠㅠ</p>
{/if} 