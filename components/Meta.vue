<template>
  <div>
    <span v-if="category" class="category">{{ category.name }}</span>
    <div class="meta">
      <span class="timestamp">
        <img src="/images/icon_clock.svg" alt height="16" width="16" />
        {{ $dayjs(createdAt).format('YYYY-MM-DD') }}
      </span>
      <span v-if="author" class="author">
        <img src="/images/icon_author.svg" alt height="16" width="16" />
        {{ author }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    createdAt: {
      type: String,
      required: true,
    },
    author: {
      type: String,
      required: false,
      default: undefined,
    },
    category: {
      type: Object,
      required: false,
      default: undefined,
    },
  },
};
</script>

<style scoped>
@media (min-width: 1024px) {
  .meta {
    padding: 10px 0 40px;
    display: flex;
    align-items: center;
  }

  .category {
    display: inline-block;
    padding: 2px 8px;
    border: 1px solid var(--color-text-sub);
    color: var(--color-text-sub);
    white-space: nowrap;
    border-radius: 3px;
    font-size: 14px;
    margin: 10px 0 2px;
  }

  .timestamp {
    display: inline-flex;
    align-items: center;
    color: var(--color-text-sub);

    margin-right: 20px;
    white-space: nowrap;

    img {
      margin-right: 6px;
      height: 16px;
    }
  }

  .author {
    display: inline-flex;
    align-items: center;
    color: var(--color-text-sub);
    white-space: nowrap;

    img {
      margin-right: 6px;
      height: 16px;
    }
  }
}
@media (max-width: 1023px) {
  .meta {
    padding: 4px 0 30px;
    font-size: 14px;
  }

  .category {
    display: inline-block;
    padding: 2px 8px;
    border: 1px solid var(--color-text-sub);
    color: var(--color-text-sub);
    white-space: nowrap;
    border-radius: 3px;
    font-size: 14px;
    margin: 10px 0 4px;
  }

  .timestamp {
    display: inline-flex;
    align-items: center;
    color: var(--color-text-sub);
    margin-right: 20px;
    white-space: nowrap;

    img {
      margin-right: 6px;
      height: 14px;
    }
  }

  .author {
    display: inline-flex;
    align-items: center;
    color: var(--color-text-sub);
    white-space: nowrap;

    img {
      margin-right: 6px;
      height: 14px;
    }
  }
}
</style>
