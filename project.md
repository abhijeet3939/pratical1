
```javascript
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

// Dummy data for doctors
const doctors = [
  { id: 1, name: 'Dr. John Doe' },
  { id: 2, name: 'Dr. Jane Smith' },
  // Add more doctors here
];

// GET /doctors - Get a list of all doctors
app.get('/doctors', (req, res) =&gt; {
  res.json(doctors);
});

// GET /doctors/:doctorId - Get details of a specific doctor
app.get('/doctors/:doctorId', (req, res) =&gt; {
  const doctorId = parseInt(req.params.doctorId);
  const doctor = doctors.find(d =&gt; d.id === doctorId);

  if (!doctor) {
    return res.status(404).json({ message: 'Doctor not found' });
  }

  res.json(doctor);
});

// POST /appointments - Book an appointment with a doctor
app.post('/appointments', (req, res) =&gt; {
  // Handle appointment booking logic here
  // Validate input, check doctor's availability, etc.
  // Return appropriate response
});

app.listen(PORT, () =&gt; {
  console.log(`Server listening on port ${PORT}`);
});
