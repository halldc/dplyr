# mde

<details>

* Version: 0.2.1
* GitHub: https://github.com/Nelson-Gon/mde
* Source code: https://github.com/cran/mde
* Date/Publication: 2020-06-27 14:40:02 UTC
* Number of recursive dependencies: 60

Run `cloud_details(, "mde")` for more info

</details>

## Newly broken

*   checking examples ... ERROR
    ```
    ...
    > # Replace NAs with 0s only for IDs in A2 and A3
    > recode_na_if(some_data,"ID",c("A2","A3"),replacement=0)
    Error: Problem with `mutate()` input `..1`.
    ✖ Input `..1` can't be recycled to size 1.
    ℹ Input `..1` is `(function (.cols = everything(), .fns = NULL, ..., .names = NULL) ...`.
    ℹ Input `..1` must be size 1, not 0.
    ℹ The error occurred in group 1: ID = "A1".
    Backtrace:
         █
      1. ├─mde::recode_na_if(some_data, "ID", c("A2", "A3"), replacement = 0)
      2. ├─mde:::recode_na_if.data.frame(...)
      3. │ └─`%>%`(...)
      4. ├─dplyr::ungroup(.)
      5. ├─dplyr::mutate(...)
      6. ├─dplyr:::mutate.data.frame(...)
      7. │ └─dplyr:::mutate_cols(.data, ...)
      8. │   ├─base::withCallingHandlers(...)
      9. │   └─mask$eval_all_mutate(quo)
     10. └─dplyr:::abort_glue(character(0), list(x_size = 0L), "dplyr:::mutate_incompatible_size")
     11.   └─rlang::exec(abort, class = class, !!!data)
    Execution halted
    ```

*   checking tests ... ERROR
    ```
      Running ‘testthat.R’
    Running the tests in ‘tests/testthat.R’ failed.
    Last 13 lines of output:
        1. ├─mde::recode_na_if(some_data, "ID", c("A2", "A3"), replacement = 0) test_recode_na_if.R:19:10
        2. ├─mde:::recode_na_if.data.frame(...)
        3. │ └─`%>%`(...)
        4. ├─dplyr::ungroup(.)
        5. ├─dplyr::mutate(...)
        6. ├─dplyr:::mutate.data.frame(...)
        7. │ └─dplyr:::mutate_cols(.data, ...)
        8. │   ├─base::withCallingHandlers(...)
        9. │   └─mask$eval_all_mutate(quo)
       10. └─dplyr:::abort_glue(character(0), list(x_size = 0L), "dplyr:::mutate_incompatible_size")
       11.   └─rlang::exec(abort, class = class, !!!data)
      
      [ FAIL 1 | WARN 2 | SKIP 0 | PASS 68 ]
      Error: Test failures
      Execution halted
    ```

