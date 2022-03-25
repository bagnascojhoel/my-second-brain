## Testing
### Integration Tests
With the annotation `@SpringBootTest` we can tell Spring Boot to run a process similar to initializing the whole application context. Using its attribute `classes = {EmployeeRepository.class, EmployeeService.class}`, it is possible to tell Spring to load only the necessary context for your test case.