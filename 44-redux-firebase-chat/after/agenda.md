# Demo: Redux Firebase Chat

1. Hello Firebase
  * Create a new service
  * Create a new app
  * Get app init code
  
2. How Firebase Works
  * Writing to a firebase collection
  * Reading from a firebase collection

3. Create an action to send a message to Firebase
  * Create the action
  * See the new message in Firebase management console

4. Create a Middleware to listen for incoming events
  * Create the middleware
  * Middleware init
  * Read all messages and create a RESET_MESSAGES object



Firebase Simple API

// Write To Firebase
const msgs = firebase.firestore().collection('messages');
msgs.add({ from, text, timestamp });


// Read From Firebase
firebase.firestore().collection('messages').orderBy('timestamp').
  onSnapshot(function(qs) {
    const batch = [];
    qs.forEach(function(doc) {
      batch.push({ id: doc.id, ...doc.data()});
    }
    /// we have the new messages in batch
    dispatch({ ... });
)
