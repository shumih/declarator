<script>
    const sidebarItems = [
        'Президент РФ',
        'Администрация Президента РФ',
        'Правительство РФ',
        'Министерства РФ',
        'Федеральные службы и агентства',
        'Совет Федерации',
        'Госдума',
        'Конституционный суд'
    ]
</script>

<style>
    .sidebar {
        display: flex;
        flex-direction: column;
    }

    .sidebar-item {
        display: flex;
        padding: 8px;
    }
    .sidebar-item-icon {
        display: block;
        margin: 0 8px;
    }
    .sidebar-item-text {
        font-family: Helvetica CE, sans-serif;
        font-size: 12px;
        line-height: 16px;
        color: var(--text-grey);
    }
    .sidebar-item-text:hover {
        cursor: pointer;
        color: var(--text-black);
    }

    .logo {
        height: 24px;
        display: flex;
        align-items: center;
        padding: 30px 20px;
    }

    .logo-text {
        margin-left: 12px;
        font-family: Helvetica CE, sans-serif;
        font-size: 14px;
        line-height: 18px;
        font-weight: bold;
        color: var(--text-black);
    }
</style>

<div class="logo">
    <img src="/assets/logo.svg" />
    <span class="logo-text">Declarator</span>
</div>
<div class="sidebar">
    {#each sidebarItems as sidebarItem}
        <div class="sidebar-item">
            <img class="sidebar-item-icon" src="/assets/sidebar-item-icon.svg" />
            <span class="sidebar-item-text">{sidebarItem}</span>
        </div>
    {/each}
</div>
