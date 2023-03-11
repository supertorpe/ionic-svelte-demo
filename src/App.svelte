  <script lang="ts">
    import './style.css';
    import './ionic';
    import iconHome from '@ionic/core/dist/ionic/svg/home.svg';
    import iconMenu from '@ionic/core/dist/ionic/svg/menu.svg';

    const ICON_MAP = ['home.svg', iconHome, 'menu.svg', iconMenu];
    document.addEventListener("DOMContentLoaded", () => {
        document.querySelectorAll('ion-icon').forEach((el: HTMLIonIconElement) => {
            const dataSrc: string | null = el.getAttribute('data-src');
            if (dataSrc != null) el.src = ICON_MAP[ICON_MAP.indexOf(dataSrc)+1];
        });
    });
  </script>
  
  <main>
    <ion-app>
        <ion-menu content-id="main-content">
        <ion-header>
            <ion-toolbar color="primary">
            <ion-title>Menu</ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content>
            <ion-list>
            <ion-list-header> Navigate </ion-list-header>
            <ion-menu-toggle auto-hide="false">
                <ion-item button>
                <ion-icon slot="start" data-src="home.svg"></ion-icon>
                <ion-label> Home </ion-label>
                </ion-item>
            </ion-menu-toggle>
            </ion-list>
        </ion-content>
        </ion-menu>

        <ion-page class="ion-page" id="main-content">
        <ion-header>
            <ion-toolbar>
            <ion-buttons slot="start">
                <ion-menu-toggle>
                <ion-button>
                    <ion-icon slot="icon-only" data-src="menu.svg"></ion-icon>
                </ion-button>
                </ion-menu-toggle>
            </ion-buttons>
            <ion-title>Header</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
            <h1>Main Content</h1>
            <p>Click the icon in the top left to toggle the menu.</p>
        </ion-content>
        </ion-page>
    </ion-app>

    <ion-menu-controller></ion-menu-controller>
  </main>