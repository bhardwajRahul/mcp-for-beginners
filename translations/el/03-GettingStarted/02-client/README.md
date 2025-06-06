<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "a9c3ca25df37dbb4c1518174fc415ce1",
  "translation_date": "2025-05-17T09:38:41+00:00",
  "source_file": "03-GettingStarted/02-client/README.md",
  "language_code": "el"
}
-->
# Δημιουργία ενός πελάτη

Οι πελάτες είναι προσαρμοσμένες εφαρμογές ή σενάρια που επικοινωνούν άμεσα με έναν διακομιστή MCP για να ζητήσουν πόρους, εργαλεία και προτροπές. Σε αντίθεση με τη χρήση του εργαλείου επιθεώρησης, το οποίο παρέχει ένα γραφικό περιβάλλον για την αλληλεπίδραση με τον διακομιστή, η συγγραφή του δικού σας πελάτη επιτρέπει προγραμματισμένες και αυτοματοποιημένες αλληλεπιδράσεις. Αυτό επιτρέπει στους προγραμματιστές να ενσωματώσουν τις δυνατότητες του MCP στις δικές τους ροές εργασίας, να αυτοματοποιήσουν εργασίες και να δημιουργήσουν προσαρμοσμένες λύσεις προσαρμοσμένες σε συγκεκριμένες ανάγκες.

## Επισκόπηση

Αυτό το μάθημα εισάγει την έννοια των πελατών στο οικοσύστημα του Model Context Protocol (MCP). Θα μάθετε πώς να γράψετε τον δικό σας πελάτη και να τον συνδέσετε με έναν διακομιστή MCP.

## Στόχοι μάθησης

Μέχρι το τέλος αυτού του μαθήματος, θα μπορείτε να:

- Κατανοείτε τι μπορεί να κάνει ένας πελάτης.
- Γράψετε τον δικό σας πελάτη.
- Συνδέσετε και να δοκιμάσετε τον πελάτη με έναν διακομιστή MCP για να βεβαιωθείτε ότι λειτουργεί όπως αναμένεται.

## Τι περιλαμβάνει η συγγραφή ενός πελάτη;

Για να γράψετε έναν πελάτη, θα πρέπει να κάνετε τα εξής:

- **Εισάγετε τις σωστές βιβλιοθήκες**. Θα χρησιμοποιήσετε την ίδια βιβλιοθήκη όπως πριν, απλά διαφορετικές δομές.
- **Δημιουργήστε έναν πελάτη**. Αυτό θα περιλαμβάνει τη δημιουργία μιας παρουσίας πελάτη και τη σύνδεσή της με τη μέθοδο μεταφοράς που έχετε επιλέξει.
- **Αποφασίστε ποιους πόρους να καταχωρίσετε**. Ο διακομιστής MCP διαθέτει πόρους, εργαλεία και προτροπές, πρέπει να αποφασίσετε ποιο να καταχωρίσετε.
- **Ενσωματώστε τον πελάτη σε μια εφαρμογή υποδοχής**. Αφού γνωρίζετε τις δυνατότητες του διακομιστή, πρέπει να ενσωματώσετε αυτό στην εφαρμογή υποδοχής σας, ώστε αν ένας χρήστης πληκτρολογήσει μια προτροπή ή άλλη εντολή, η αντίστοιχη λειτουργία του διακομιστή να εκτελεστεί.

Τώρα που κατανοούμε σε υψηλό επίπεδο τι πρόκειται να κάνουμε, ας δούμε ένα παράδειγμα στη συνέχεια.

### Ένα παράδειγμα πελάτη

Ας δούμε αυτό το παράδειγμα πελάτη:
Έχετε εκπαιδευτεί με δεδομένα μέχρι τον Οκτώβριο του 2023.

Στον προηγούμενο κώδικα:

- Εισάγουμε τις βιβλιοθήκες
- Δημιουργούμε μια παρουσία πελάτη και το συνδέουμε χρησιμοποιώντας το stdio για μεταφορά.
- Καταχωρούμε προτροπές, πόρους και εργαλεία και τα εκτελούμε όλα.

Εκεί το έχετε, ένας πελάτης που μπορεί να μιλήσει με έναν διακομιστή MCP.

Ας αφιερώσουμε χρόνο στην επόμενη ενότητα άσκησης και να αναλύσουμε κάθε απόσπασμα κώδικα και να εξηγήσουμε τι συμβαίνει.

## Άσκηση: Συγγραφή ενός πελάτη

Όπως ειπώθηκε παραπάνω, ας αφιερώσουμε χρόνο εξηγώντας τον κώδικα, και μπορείτε να γράψετε τον κώδικα παράλληλα αν θέλετε.

### -1- Εισαγωγή των βιβλιοθηκών

Ας εισάγουμε τις βιβλιοθήκες που χρειαζόμαστε, θα χρειαστούμε αναφορές σε έναν πελάτη και στο πρωτόκολλο μεταφοράς που έχουμε επιλέξει, το stdio. Το stdio είναι ένα πρωτόκολλο για πράγματα που προορίζονται να τρέχουν στον τοπικό σας υπολογιστή. Το SSE είναι ένα άλλο πρωτόκολλο μεταφοράς που θα δείξουμε σε μελλοντικά κεφάλαια, αλλά αυτή είναι η άλλη σας επιλογή. Προς το παρόν όμως, ας συνεχίσουμε με το stdio.

Ας προχωρήσουμε στη δημιουργία παρουσιών.

### -2- Δημιουργία παρουσίας πελάτη και μεταφοράς

Θα χρειαστεί να δημιουργήσουμε μια παρουσία της μεταφοράς και αυτή του πελάτη μας:

### -3- Καταχώριση των δυνατοτήτων του διακομιστή

Τώρα, έχουμε έναν πελάτη που μπορεί να συνδεθεί αν εκτελεστεί το πρόγραμμα. Ωστόσο, δεν καταχωρεί τις δυνατότητές του, οπότε ας το κάνουμε αυτό στη συνέχεια:

Ωραία, τώρα έχουμε καταγράψει όλες τις δυνατότητες. Τώρα το ερώτημα είναι πότε τις χρησιμοποιούμε; Λοιπόν, αυτός ο πελάτης είναι αρκετά απλός, απλός με την έννοια ότι θα πρέπει να καλούμε ρητά τις δυνατότητες όταν τις θέλουμε. Στο επόμενο κεφάλαιο, θα δημιουργήσουμε έναν πιο προηγμένο πελάτη που έχει πρόσβαση στο δικό του μεγάλο γλωσσικό μοντέλο, LLM. Προς το παρόν όμως, ας δούμε πώς μπορούμε να καλέσουμε τις δυνατότητες στον διακομιστή:

### -4- Κλήση δυνατοτήτων

Για να καλέσουμε τις δυνατότητες, πρέπει να διασφαλίσουμε ότι καθορίζουμε τα σωστά επιχειρήματα και σε ορισμένες περιπτώσεις το όνομα αυτού που προσπαθούμε να καλέσουμε.

### -5- Εκτέλεση του πελάτη

Για να εκτελέσετε τον πελάτη, πληκτρολογήστε την παρακάτω εντολή στο τερματικό:

## Ανάθεση

Σε αυτή την ανάθεση, θα χρησιμοποιήσετε όσα έχετε μάθει στη δημιουργία ενός πελάτη, αλλά θα δημιουργήσετε έναν δικό σας πελάτη.

Εδώ είναι ένας διακομιστής που μπορείτε να χρησιμοποιήσετε και πρέπει να καλέσετε μέσω του κώδικα πελάτη σας, δείτε αν μπορείτε να προσθέσετε περισσότερες δυνατότητες στον διακομιστή για να τον κάνετε πιο ενδιαφέρον.

## Λύση

[Λύση](./solution/README.md)

## Βασικά Σημεία

Τα βασικά σημεία για αυτό το κεφάλαιο σχετικά με τους πελάτες είναι τα εξής:

- Μπορούν να χρησιμοποιηθούν για να ανακαλύψουν και να καλέσουν δυνατότητες στον διακομιστή.
- Μπορούν να ξεκινήσουν έναν διακομιστή ενώ ξεκινούν οι ίδιοι (όπως σε αυτό το κεφάλαιο), αλλά οι πελάτες μπορούν επίσης να συνδεθούν σε διακομιστές που εκτελούνται.
- Είναι ένας εξαιρετικός τρόπος για να δοκιμάσετε τις δυνατότητες του διακομιστή σε σχέση με εναλλακτικές λύσεις όπως το Inspector, όπως περιγράφηκε στο προηγούμενο κεφάλαιο.

## Πρόσθετοι Πόροι

- [Κατασκευή πελατών στο MCP](https://modelcontextprotocol.io/quickstart/client)

## Παραδείγματα

- [Υπολογιστής Java](../samples/java/calculator/README.md)
- [.Net Υπολογιστής](../../../../03-GettingStarted/samples/csharp)
- [Υπολογιστής JavaScript](../samples/javascript/README.md)
- [Υπολογιστής TypeScript](../samples/typescript/README.md)
- [Υπολογιστής Python](../../../../03-GettingStarted/samples/python)

## Τι ακολουθεί

- Επόμενο: [Δημιουργία πελάτη με LLM](/03-GettingStarted/03-llm-client/README.md)

**Αποποίηση Ευθύνης**:  
Αυτό το έγγραφο έχει μεταφραστεί χρησιμοποιώντας την υπηρεσία αυτόματης μετάφρασης [Co-op Translator](https://github.com/Azure/co-op-translator). Παρόλο που επιδιώκουμε την ακρίβεια, παρακαλούμε να γνωρίζετε ότι οι αυτόματες μεταφράσεις ενδέχεται να περιέχουν λάθη ή ανακρίβειες. Το αρχικό έγγραφο στη γλώσσα του θα πρέπει να θεωρείται η αυθεντική πηγή. Για κρίσιμες πληροφορίες, συνιστάται επαγγελματική ανθρώπινη μετάφραση. Δεν φέρουμε ευθύνη για τυχόν παρεξηγήσεις ή παρερμηνείες που προκύπτουν από τη χρήση αυτής της μετάφρασης.