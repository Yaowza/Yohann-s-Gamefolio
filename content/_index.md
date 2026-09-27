<dialog id="profile-dialog" class="profile-dialog" aria-labelledby="profile-dialog-title">
  <div class="profile-dialog__content">
    <button id="profile-dialog-close" class="profile-dialog__close" type="button">
      Close
    </button>
    <img id="profile-dialog-avatar" class="profile-dialog__avatar" alt="">
    <h1 id="profile-dialog-title">Yohann Perrette</h1>
    <h2 id="profile-dialog-subtitle1">Who am I ?</h2>
    <p>
  Creative 23-year-old Game Design graduate, I dedicate part of my time to building my own video game studio alongside my team.

  As a Game Designer, I have a solid command of all core design fields (Level Design, System Design,UX, and more).

  Specialized in Unreal Engine, I excel at integrating and optimizing VFX—notably using Niagara—while also creating my own custom visual effects. I program fluently in Blueprints and have working knowledge of C++.

  Additionally, I have foundational skills in Blender for 3D modeling and Reaper for sound design.
    </p>
  </div>
</dialog>

<script>
(() => {
  const dialog = document.getElementById("profile-dialog");
  const avatar = [...document.querySelectorAll("img[alt]")]
    .find((image) => image.alt.trim() === "Yohann Perrette");

  if (!dialog || !avatar) return;

  const dialogAvatar = document.getElementById("profile-dialog-avatar");
  dialogAvatar.src = avatar.currentSrc || avatar.src;
  dialogAvatar.alt = avatar.alt;

  avatar.classList.add("profile-avatar-trigger");
  avatar.setAttribute("role", "button");
  avatar.setAttribute("tabindex", "0");
  avatar.setAttribute("aria-haspopup", "dialog");
  avatar.setAttribute("aria-label", "Afficher ma présentation");

  avatar.addEventListener("click", (event) => {
    event.preventDefault();
    event.stopImmediatePropagation();
    dialog.showModal();
  }, true);

  avatar.addEventListener("keydown", (event) => {
    if (event.key === "Enter" || event.key === " ") {
      event.preventDefault();
      dialog.showModal();
    }
  });

  document.getElementById("profile-dialog-close")
    .addEventListener("click", () => dialog.close());

  dialog.addEventListener("click", (event) => {
    if (event.target === dialog) dialog.close();
  });
})();
</script>


