<template>
    <section class="bg-green-50">
        <div class="container m-auto py-10 px-6">
            <div class="grid grid-cols-1 md:grid-cols-70/30 w-full gap-6">
                <main>
                    <div class="bg-white p-6 rounded-lg shadow-md text-center md:text-left">
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <div class="text-gray-500 mb-4 flex align-middle justify-center md:justify-start"><i
                                class="fa-solid fa-location-dot text-lg text-orange-700 mr-2"></i>
                                <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                            </div>
                    </div>
                    <div class="bg-white p-6 rounded-lg shadow-md mt-6">
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />

                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                    </div>
                </main><!-- Sidebar -->
                <aside><!-- Company Info -->
                    <div class="bg-white p-6 rounded-lg shadow-md">
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />

                        <hr class="my-4">
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                    </div><!-- Manage -->
                    <div class="bg-white p-6 rounded-lg shadow-md mt-6">
                        <h3 class="text-xl font-bold mb-6"><WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        </h3><a href="add-job.html"
                            class="bg-green-500 hover:bg-green-600 text-white text-center font-bold py-2 px-4 rounded-full w-full focus:outline-none focus:shadow-outline mt-4 block">
                            <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        </a><button
                            class="bg-red-500 hover:bg-red-600 text-white font-bold py-2 px-4 rounded-full w-full focus:outline-none focus:shadow-outline mt-4 block">
                            <WidgetsSkeletonLoader height="20px" width="50%" class="mb-3" />
                        </button>
                    </div>
                </aside>
            </div>
        </div>
    </section>
</template>

<script setup>
</script>