<script>
  import { getValidation, Form, Slide, Entry } from 'helpers/helpers';

  const getConfig = (params) => {
    return { entries: [{ type: 'string', ...params }] }
  };

  const {
    entries: [minEntry],
    createForm: minCreateForm
  } = getValidation(getConfig({ min: 2 }));

  const {
    entries: [maxEntry],
    createForm: maxCreateForm
  } = getValidation(getConfig({ max: 6 }));

  const {
    entries: [betweenEntry],
    createForm: betweenCreateForm
  } = getValidation(getConfig({ between: [2,5] }));

  let activeId = 'min';
</script>

<Slide id="min" bind:activeId>
  <Form createForm={minCreateForm}>
    <Entry entry={minEntry} />
  </Form>
</Slide>

<Slide id="max" bind:activeId>
  <Form createForm={maxCreateForm}>
    <Entry entry={maxEntry} />
  </Form>
</Slide>

<Slide id="between" bind:activeId>
  <Form createForm={betweenCreateForm}>
    <Entry entry={betweenEntry} />
  </Form>
</Slide>
