## resources/js/bootstrap.js

// @see CTR-146 - Uncomment when ready to use Pusher on frontend
// import Echo from 'laravel-echo'
// import Pusher from 'pusher-js'
// window.Pusher = Pusher

## resources/js/bootstrap.js


// @see CTR-146 - Uncomment when ready to use Pusher on frontend
// window.Echo = new Echo({
//     broadcaster: 'pusher',
//     key: import.meta.env.VITE_PUSHER_APP_KEY,
//     wsHost: window.location.hostname,
//     wsPort: import.meta.env.VITE_PUSHER_PORT,
//     wssPort: import.meta.env.VITE_PUSHER_PORT ?? 443,
//     forceTLS: false,
//     cluster: import.meta.env.VITE_PUSHER_APP_CLUSTER,
//     // enabledTransports: ['ws', 'wss'],
// })

## resources/js/Layouts/AppLayout.vue


// @see CTR-146 - Uncomment when ready to use Pusher on frontend
// const event = 'NotifyUser'
// const channel = 'App.Models.User.' + Inertia.page.props.user.id
// console.log(`Broadcast listening on channel '${channel}' for ${event} event`)
//
// window.Echo
//     .private(channel)
//     .listen(event, (e) => {
//         console.log(e)
//         alert(`${event} : ${e.message}  User: ${e.user.name}`)
//     })
