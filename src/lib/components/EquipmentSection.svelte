<script>
  import { t } from '$lib/translations';
  import Button from './Button.svelte';
  import ResponsiveImage from './ResponsiveImage.svelte';
  import SecondaryBox from './SecondaryBox.svelte';
  import { getModalStore } from '@skeletonlabs/skeleton';
  const modalStore = getModalStore();
</script>

<SecondaryBox>
  <div class="flex flex-col justify-between gap-y-6 p-2 md:h-[300px] md:flex-row md:p-8">
    <div class="flex h-full w-full flex-col justify-between md:w-1/2">
      <h2 class="m-0">{$t('common.contact.title')}</h2>
      <Button
        class="w-full max-w-[8rem] self-end md:max-w-[14rem] md:self-start"
        on:click={() =>
          modalStore.trigger({
            component: 'formModal',
            type: 'component',
            title: "Let's Talk"
          })}
      >
        {$t('common.contact.cta')}
      </Button>
    </div>
    <ResponsiveImage
      src="equipment.svg"
      alt="Equipment"
      class="relative -top-4 h-[340px]"
      showOnMobile={false}
    />
  </div>
</SecondaryBox>
