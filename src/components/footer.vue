<template>
    <footer class="footer">
        <div class="container mx-auto py-8">
            <div class="flex justify-between items-center">
                <div>
                    <p class="text-lg font-bold">Mobile Master</p>
                    <p class="text-sm">© 2023 Mobile Master. Derechos reservados.</p>
                </div>
                <div>
                    <p class="text-sm text-gray-300">Siguenos:</p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-blue-500 hover:underline">Facebook</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>

export default {

}
</script>

<style scoped>
.footer {
    background-color: #333;
    color: white;
}

.footer p {
    margin: 0;
}

.footer a {
    color: white;
}

.footer a:hover {
    text-decoration: underline;
}
</style>