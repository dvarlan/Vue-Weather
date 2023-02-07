<template>
    <div>
        <Particles
            id="tsparticles"
            :particlesInit="particlesInit"
            :particlesLoaded="particlesLoaded"
            :options="{
                    background: {
                        color: {
                            value: '#1E1E1E'
                        }
                    },
                    fullScreen: {
                        enable: true,
                        zIndex: -1
                    },
                    fpsLimit: 240,
                    smooth: true,
                    interactivity: {
                        events: {
                            onClick: {
                                enable: false,
                            },
                            onHover: {
                                enable: true,
                                mode: ['grab', 'connect']
                            },
                            resize: false
                        },
                        modes: {
                            bubble: {
                                distance: 400,
                                duration: 2,
                                opacity: 0.8,
                                size: 40
                            },
                            push: {
                                quantity: 4
                            },
                            repulse: {
                                distance: 200,
                                duration: 0.4
                            }
                        }
                    },
                    particles: {
                        color: {
                            value: '#ffffff'
                        },
                        links: {
                            color: '#B2CFCF',
                            distance: 150,
                            enable: true,
                            opacity: 0.5,
                            width: 1
                        },
                        collisions: {
                            enable: true
                        },
                        move: {
                            direction: 'none',
                            enable: true,
                            outMode: 'bounce',
                            random: false,
                            speed: 2,
                            straight: false
                        },
                        number: {
                            density: {
                                enable: true,
                                area: 1200
                            },
                            value: 80
                        },
                        opacity: {
                            value: 0.5
                        },
                        shape: {
                            type: 'circle'
                        },
                        size: {
                            random: true,
                            value: 5
                        }
                    },
                    detectRetina: true
                }"
        />
    </div>
</template>

<script setup>
import { loadFull } from "tsparticles";

const particlesInit = async engine => {
    await loadFull(engine);
};

const particlesLoaded = async container => {
    console.log("Particles container loaded", container);
};
</script>