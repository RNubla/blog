<template>

    <div class="bg-base-200 flex flex-col min-h-screen">
        <Navbar class="mb-2" />
        <main class="mx-auto max-w-7xl md:px-2 flex-grow">
            <slot></slot>
        </main>
        <Footer />
    </div>
</template>

