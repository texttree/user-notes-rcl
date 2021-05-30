```jsx
import React, { useState } from "react";

import { Button, Dialog, DialogTitle } from "@material-ui/core";

import { SendNote } from "@texttree/tsv-frontend";

const [openDialog, setOpenDialog] = useState(false);
const [answerSend, setAnswerSend] = useState({});
const handleclick = () => {
  const answer = SendNote({
    reference: "2:1",
    bookId: "en",
    resource: "rlob",
    serverLink: "https://lit-falls-48214.herokuapp.com/send-to-file",
    type: "err",
  });
  setOpenDialog(true);
  setAnswerSend(answer);
};
const handleClose = () => {
  setOpenDialog(false);
};
<>
  <Button variant="contained" onClick={handleclick}>
    Send to TSV file
  </Button>
  <Dialog open={openDialog} onClose={handleClose}>
    <DialogTitle>{answerSend.message}</DialogTitle>
  </Dialog>
</>;
```