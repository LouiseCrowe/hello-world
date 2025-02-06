    //CONTROLLER
    @PutMapping("{id}")
    public ResponseEntity<?> updateStudent(@PathVariable long id, @RequestBody Student student) {
        Optional<Student> optionalStudent = this.studentService.updateStudent(id, student);
        if(optionalStudent.isPresent()) {
            return ResponseEntity.ok(optionalStudent.get());
        }
        return ResponseEntity.notFound().build();
    }

    @DeleteMapping("{id}")
    public void deleteStudentById(@PathVariable long id) {
        this.studentService.deleteStudentById(id);
    }



    //SERVICE
    // update student
    public Optional<Student> updateStudent(long id, Student updatedStudent) {
        Optional<Student> existingStudent = this.studentRepository.findById(id);
        if(existingStudent.isPresent()) {
            Student student = existingStudent.get();
            student.setAge(updatedStudent.getAge());
            student.setName(updatedStudent.getName());
            student.setEmail(updatedStudent.getEmail());
            return Optional.of(this.studentRepository.save(student));
        } else {
            return Optional.empty();
        }
    }

    // delete course
    public void deleteStudentById(long id) {
        this.studentRepository.deleteById(id);
    }
