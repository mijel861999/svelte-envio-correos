<script>
    //   import { page } from '$app/stores';
    import { Sidebar, SidebarBrand, SidebarCta, SidebarDropdownItem, SidebarDropdownWrapper, SidebarGroup, SidebarItem, SidebarWrapper } from 'flowbite-svelte';
  import { Link } from 'svelte-routing';
    // import { ChartPieSolid, GridSolid, MailBoxSolid, UserSolid, ArrowRightToBracketSolid, FileEditSolid } from 'flowbite-svelte-icons';
    let activeUrl =  window.location.pathname;
    console.log(activeUrl)
    let spanClass = 'flex-1 ms-3 whitespace-nowrap';

    function isActiveLink(linkPath) {
        return activeUrl === linkPath;
    }
</script>

<div class="flex h-screen">
    <Sidebar {activeUrl} class="max-h-screen h-screen">
        <SidebarWrapper class="h-screen">
          <SidebarGroup>
            <Link to="/">
                <SidebarItem label="Home">
                    <svelte:fragment slot="icon">
                        <!-- <ChartPieSolid class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" /> -->
                    </svelte:fragment>
                </SidebarItem>
            </Link>
            <Link to="/correos">
                <SidebarItem label="Correos">
                    <svelte:fragment slot="icon">
                        <!-- <ChartPieSolid class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" /> -->
                    </svelte:fragment>
                </SidebarItem>
            </Link>
            <Link to="/grupos">
                <SidebarItem label="Grupos">
                    <svelte:fragment slot="icon">
                        <!-- <ChartPieSolid class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" /> -->
                    </svelte:fragment>
                </SidebarItem>
            </Link>
            <Link to="/envio">
                <SidebarItem label="Envio de correos">
                    <svelte:fragment slot="icon">
                        <!-- <ChartPieSolid class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" /> -->
                    </svelte:fragment>
                </SidebarItem>
            </Link>
          </SidebarGroup>
        </SidebarWrapper>
      </Sidebar>
      <div class="m-9 w-full">
          <slot />
      </div>
</div>
