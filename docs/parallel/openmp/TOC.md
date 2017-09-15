# [OpenMP en Visual C++](openmp-in-visual-cpp.md)
# [Interfaz de programación de aplicaciones de OpenMP C y C++](openmp-c-and-cpp-application-program-interface.md)
## [Contenido](contents.md)
## [1. Introducción](1-introduction.md)
### [1.1 Ámbito](1-1-scope.md)
### [1.2 Definición de términos](1-2-definition-of-terms.md)
### [1.3 Modelo de ejecución](1-3-execution-model.md)
### [1.4 Conformidad](1-4-compliance.md)
### [1.5 Referencias de normativa](1-5-normative-references.md)
### [1.6 Organización](1-6-organization.md)
## [2. Directivas](2-directives.md)
### [2.1 Formato de directivas](2-1-directive-format.md)
### [2.2 Compilación condicional](2-2-conditional-compilation.md)
### [2.3 parallel (construcción)](2-3-parallel-construct.md)
### [2.4 Construcciones de uso compartido](2-4-work-sharing-constructs.md)
#### [2.4.1 for (construcción)](2-4-1-for-construct.md)
#### [2.4.2 sections (construcción)](2-4-2-sections-construct.md)
#### [2.4.3 single (construcción)](2-4-3-single-construct.md)
### [2.5 Construcciones de uso compartido paralelas combinadas](2-5-combined-parallel-work-sharing-constructs.md)
#### [2.5.1 parallel for (construcción)](2-5-1-parallel-for-construct.md)
#### [2.5.2 parallel sections (construcción)](2-5-2-parallel-sections-construct.md)
### [2.6 Directivas maestras y de sincronización](2-6-master-and-synchronization-directives.md)
#### [2.6.1 master (construcción)](2-6-1-master-construct.md)
#### [2.6.2 critical (construcción)](2-6-2-critical-construct.md)
#### [2.6.3 barrier (directiva)](2-6-3-barrier-directive.md)
#### [2.6.4 atomic (construcción)](2-6-4-atomic-construct.md)
#### [2.6.5 flush (directiva)](2-6-5-flush-directive.md)
#### [2.6.6 ordered (construcción)](2-6-6-ordered-construct.md)
### [2.7 Entorno de datos](2-7-data-environment.md)
#### [2.7.1 threadprivate (directiva)](2-7-1-threadprivate-directive.md)
#### [2.7.2 Cláusulas de atributos de uso compartido de datos](2-7-2-data-sharing-attribute-clauses.md)
##### [2.7.2.1 private](2-7-2-1-private.md)
##### [2.7.2.2 firstprivate](2-7-2-2-firstprivate.md)
##### [2.7.2.3 lastprivate](2-7-2-3-lastprivate.md)
##### [2.7.2.4 shared](2-7-2-4-shared.md)
##### [2.7.2.5 default](2-7-2-5-default.md)
##### [2.7.2.6 reduction](2-7-2-6-reduction.md)
##### [2.7.2.7 copyin](2-7-2-7-copyin.md)
##### [2.7.2.8 copyprivate](2-7-2-8-copyprivate.md)
### [2.8 Enlace de directivas](2-8-directive-binding.md)
### [2.9 Anidamiento de directivas](2-9-directive-nesting.md)
## [3. Funciones de biblioteca en tiempo de ejecución](3-run-time-library-functions.md)
### [3.1 Funciones de entorno de ejecución](3-1-execution-environment-functions.md)
#### [3.1.1 omp_set_num_threads (función)](3-1-1-omp-set-num-threads-function.md)
#### [3.1.2 omp_get_num_threads (función)](3-1-2-omp-get-num-threads-function.md)
#### [3.1.3 omp_get_max_threads (función)](3-1-3-omp-get-max-threads-function.md)
#### [3.1.4 omp_get_thread_num (función)](3-1-4-omp-get-thread-num-function.md)
#### [3.1.5 omp_get_num_procs (función)](3-1-5-omp-get-num-procs-function.md)
#### [3.1.6 omp_in_parallel (función)](3-1-6-omp-in-parallel-function.md)
#### [3.1.7 omp_set_dynamic (función)](3-1-7-omp-set-dynamic-function.md)
#### [3.1.8 omp_get_dynamic (función)](3-1-8-omp-get-dynamic-function.md)
#### [3.1.9 omp_set_nested (función)](3-1-9-omp-set-nested-function.md)
#### [3.1.10 omp_get_nested (función)](3-1-10-omp-get-nested-function.md)
### [3.2 Funciones de bloqueo](3-2-lock-functions.md)
#### [3.2.1 omp_init_lock y omp_init_nest_lock (funciones)](3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)
#### [3.2.2 omp_destroy_lock y omp_destroy_nest_lock (funciones)](3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)
#### [3.2.3 omp_set_lock y omp_set_nest_lock (funciones)](3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)
#### [3.2.4 omp_unset_lock y omp_unset_nest_lock (funciones)](3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)
#### [3.2.5 omp_test_lock y omp_test_nest_lock (funciones)](3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)
### [3.3 Rutinas temporales](3-3-timing-routines.md)
#### [3.3.1 omp_get_wtime (función)](3-3-1-omp-get-wtime-function.md)
#### [3.3.2 omp_get_wtick (función)](3-3-2-omp-get-wtick-function.md)
## [4. Variables de entorno](4-environment-variables.md)
### [4.1 OMP_SCHEDULE](4-1-omp-schedule.md)
### [4.2 OMP_NUM_THREADS](4-2-omp-num-threads.md)
### [4.3 OMP_DYNAMIC](4-3-omp-dynamic.md)
### [4.4 OMP_NESTED](4-4-omp-nested.md)
## [A. Ejemplos](a-examples.md)
### [A.1 Ejecutar un bucle sencillo en paralelo](a-1-executing-a-simple-loop-in-parallel.md)
### [A.2 Especificar una compilación condicional](a-2-specifying-conditional-compilation.md)
### [A.3 Usar regiones paralelas](a-3-using-parallel-regions.md)
### [A.4 Usar la cláusula nowait](a-4-using-the-nowait-clause.md)
### [A.5 Usar la directiva critical](a-5-using-the-critical-directive.md)
### [A.6 Usar la cláusula lastprivate](a-6-using-the-lastprivate-clause.md)
### [A.7 Usar la cláusula reduction](a-7-using-the-reduction-clause.md)
### [A.8 Especificar secciones paralelas](a-8-specifying-parallel-sections.md)
### [A.9 Usar directivas single](a-9-using-single-directives.md)
### [A.10 Especificar un orden secuencial](a-10-specifying-sequential-ordering.md)
### [A.11 Especificar un número fijo de subprocesos](a-11-specifying-a-fixed-number-of-threads.md)
### [A.12 Usar la directiva atomic](a-12-using-the-atomic-directive.md)
### [A.13 Usar la directiva flush con una lista](a-13-using-the-flush-directive-with-a-list.md)
### [A.14 Usar la directiva flush sin una lista](a-14-using-the-flush-directive-without-a-list.md)
### [A.15 Determinar el número de subprocesos usados](a-15-determining-the-number-of-threads-used.md)
### [A.16 Usar bloqueos](a-16-using-locks.md)
### [A.17 Usar bloqueos anidables](a-17-using-nestable-locks.md)
### [A.18 Directivas for anidadas](a-18-nested-for-directives.md)
### [A.19 Ejemplos donde se muestra un anidamiento incorrecto de directivas de uso compartido](a-19-examples-showing-incorrect-nesting-of-work-sharing-directives.md)
### [A.20 Enlace de directivas barrier](a-20-binding-of-barrier-directives.md)
### [A.21 Variables de ámbito con la cláusula private](a-21-scoping-variables-with-the-private-clause.md)
### [A.22 Usar la cláusula default(none)](a-22-using-the-default-none-clause.md)
### [A.23 Ejemplos de la directiva ordered](a-23-examples-of-the-ordered-directive.md)
### [A.24 Ejemplo de la cláusula private](a-24-example-of-the-private-clause.md)
### [A.25 Ejemplos de la cláusula de atributos de datos copyprivate](a-25-examples-of-the-copyprivate-data-attribute-clause.md)
### [A.26 Usar la directiva threadprivate](a-26-using-the-threadprivate-directive.md)
### [A.27 Uso de matrices de longitud Variable C99](a-27-use-of-c99-variable-length-arrays.md)
### [A.28 Uso de la cláusula num_threads](a-28-use-of-num-threads-clause.md)
### [A.29 Uso de construcciones de uso compartido en una construcción critical](a-29-use-of-work-sharing-constructs-inside-a-critical-construct.md)
### [A.30 Uso de la reprivatización](a-30-use-of-reprivatization.md)
### [A.31 Funciones de bloqueo seguras para subprocesos](a-31-thread-safe-lock-functions.md)
## [B. Códigos auxiliares para funciones de biblioteca en tiempo de ejecución](b-stubs-for-run-time-library-functions.md)
## [C. Gramática de OpenMP C y C++](c-openmp-c-and-cpp-grammar.md)
### [C.1 Notación](c-1-notation.md)
### [C.2 Reglas](c-2-rules.md)
## [D. Usar la cláusula schedule](d-using-the-schedule-clause.md)
## [E. Comportamientos definidos por la implementación de OpenMP C/C++](e-implementation-defined-behaviors-in-openmp-c-cpp.md)
## [F. Nuevas características y aclaraciones de la versión 2.0](f-new-features-and-clarifications-in-version-2-0.md)
# [Referencia](reference/toc.md)