# Elixir Linter Rules

###### Below is a list of rules we use for our `credo.exs`.
###### this is adapted from credo [here](https://github.com/rrrene/elixir-style-guide#the-actual-guide)

* [Consistency.ExceptionNames](#Consistency.ExceptionNames)
* [Consistency.LineEndings](#Consistency.LineEndings)
* [Consistency.SpaceAroundOperators](#Consistency.SpaceAroundOperators)
* [Consistency.SpaceInParentheses](#Consistency.SpaceInParentheses)
* [Consistency.TabsOrSpaces](#Consistency.TabsOrSpaces)
* [Design.TagFIXME](#Design.TagFIXME)
* [Design.TagTODO](#Design.TagTODO)
* [Readability.FunctionNames](#Readability.FunctionNames)
* [Readability.LargeNumbers](#Readability.LargeNumbers)
* [Readability.MaxLineLength](#Readability.MaxLineLength)
* [Readability.ModuleAttributeNames](#Readability.ModuleAttributeNames)
* [Readability.ModuleDoc](#Readability.ModuleDoc)
* [Readability.ModuleNames](#Readability.ModuleNames)
* [Readability.ParenthesesInCondition](#Readability.ParenthesesInCondition)
* [Readability.PredicateFunctionNames](#Readability.PredicateFunctionNames)
* [Readability.TrailingBlankLine](#Readability.TrailingBlankLine)
* [Readability.TrailingWhiteSpace](#Readability.TrailingWhiteSpace)
* [Readability.VariableNames](#Readability.VariableNames)
* [Refactor.ABCSize](#Refactor.ABCSize)
* [Refactor.CondStatements](#Refactor.CondStatements)
* [Refactor.CyclomaticComplexity](#Refactor.CyclomaticComplexity)
* [Refactor.FunctionArity](#Refactor.FunctionArity)
* [Refactor.MatchInCondition](#Refactor.MatchInCondition)
* [Refactor.NegatedConditionsInUnless](#Refactor.NegatedConditionsInUnless)
* [Refactor.NegatedConditionsWithElse](#Refactor.NegatedConditionsWithEls)
* [Refactor.Nesting](#Refactor.Nesting)
* [Refactor.PipeChainStart](#Refactor.PipeChainStart)
* [Refactor.UnlessWithElse](#Refactor.UnlessWithElse)
* [Warning.BoolOperationOnSameValues](#Warning.BoolOperationOnSameValues)
* [Warning.IExPry](#Warning.IExPry)
* [Warning.IoInspect](#Warning.IoInspect)
* [Warning.NameRedeclarationByAssignment](#Warning.NameRedeclarationByAssignment)
* [Warning.NameRedeclarationByCase](#Warning.NameRedeclarationByCase)
* [Warning.NameRedeclarationByDef](#Warning.NameRedeclarationByDef)
* [Warning.NameRedeclarationByFn](#Warning.NameRedeclarationByFn)
* [Warning.OperationOnSameValues](#Warning.OperationOnSameValues)
* [Warning.OperationWithConstantResult](#Warning.OperationWithConstantResult)
* [Warning.UnusedEnumOperation](#Warning.UnusedEnumOperation)
* [Warning.UnusedKeywordOperation](#Warning.UnusedKeywordOperation)
* [Warning.UnusedListOperation](#Warning.UnusedListOperation)
* [Warning.UnusedStringOperation](#Warning.UnusedStringOperation)
* [Warning.UnusedTupleOperation](#Warning.UnusedTupleOperation)

## Consistency.ExceptionNames
  * Exception names should have a common prefix or suffix, a common choice is have all of them end in `Error`
  [read more](https://github.com/rrrene/elixir-style-guide#exception-naming)

## Consistency.LineEndings
  * Use line-endings consistently (Unix-style line endings are preferred)
  [read more](https://github.com/rrrene/elixir-style-guide)

## Consistency.SpaceAroundOperators
  * Use spaces around operators and after commas
  [read more](https://github.com/rrrene/elixir-style-guide#spaces-operators)

## Consistency.SpaceInParentheses
  * Don't use spaces after `(`, `[`, and `{` or before `}`, `]`, and `)`
  [read more](https://github.com/rrrene/elixir-style-guide#spaces-braces)

## Consistency.TabsOrSpaces
  * 2 spaces soft-tabs are preferred
  [read more](https://github.com/rrrene/elixir-style-guide#spaces-indentation)

## Design.TagTODO
  * Use `TODO:` comments to plan changes to your code
  [read more](https://github.com/rrrene/elixir-style-guide#todo)

## Design.TagFIXME
  * Use `FIXME:` comments to plan changes to your code
  [read more](https://github.com/rrrene/elixir-style-guide#todo)

## Readability.FunctionNames
  * Function and macro names are always written in snake_case in Elixir
  [read more](https://github.com/rrrene/elixir-style-guide#snake-case-attributes-functions-macros-vars)

## Readability.LargeNumbers
  * Numbers can contain underscores for readability purposes
  [read more](https://github.com/rrrene/elixir-style-guide#underscores-in-numerics)

## Readability.MaxLineLength
  * Checks for the length of lines. (max 80)
  [read more](https://github.com/rrrene/elixir-style-guide#character-per-line-limit)

## Readability.ModuleAttributeNames
  * Module attribute names are always written in snake_case in Elixir
  [read more](https://github.com/rrrene/elixir-style-guide#camelcase-modules)

## Readability.ModuleDoc
  * Every module should contain comprehensive documentation
  [read more](https://github.com/rrrene/elixir-style-guide#documentation)

## Readability.ModuleNames
  * Module names are always written in PascalCase in Elixir
  [read more](https://github.com/rrrene/elixir-style-guide#naming)

## Readability.ParenthesesInCondition
  * Because `if` and `unless` are macros, the preferred style is to not use parentheses around conditions.
  [read more](https://github.com/rrrene/elixir-style-guide#macro-parens)

## Readability.PredicateFunctionNames
  * Predicate functions/macros should return a boolean value, for functions, they should end in a question mark.
  ```
  # preferred way
  def valid?(username) do
    # ...
  end

  # NOT okay
  def is_valid?(username) do
    # ...
  end
  ```
  [read more](https://github.com/rrrene/elixir-style-guide#predicates)

## Readability.TrailingBlankLine
  * Files should end in a trailing blank line
  [read more](https://github.com/rrrene/elixir-style-guide#newline-eof)

## Readability.TrailingWhiteSpace
  *  There should be no white-space (i.e. tabs, spaces) at the end of a line
  [read more](https://github.com/rrrene/elixir-style-guide#no-trailing-whitespace)

## Readability.VariableNames
  * Variable names are always written in snake_case in Elixir
  [read more](https://github.com/rrrene/elixir-style-guide#snake-case-attributes-functions-macros-vars)

## Refactor.ABCSize
  * The ABC size describes a metric based on assignments, branches and conditions.
  * A high ABC size is a hint that a function might be doing "more" than it should.
  [read more](https://github.com/rrrene/elixir-style-guide#refactoring-opportunities)

## Refactor.CondStatements
  * Each cond statement should have 3 or more statements including the "always true" statement.
  [read more](https://github.com/rrrene/elixir-style-guide#refactoring-opportunities)

## Refactor.FunctionArity
  *  A function can take as many parameters as needed, but even in a functional language
  there can be too many parameters.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/function_arity.ex)

## Refactor.MatchInCondition
  * Pattern matching should only ever be used for simple assignments inside `if` and `unless` clauses.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/match_in_condition.ex)

## Refactor.PipeChainStart
  * Pipes (`|>`) can become more readable by starting with a "raw" value.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/pipe_chain_start.ex)

## Refactor.CyclomaticComplexity
  * Cyclomatic complexity is a software complexity metric closely correlated with coding errors
  * If a function feels like it's gotten too complex, it more often than not also has a high CC value
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/cyclomatic_complexity.ex)

## Refactor.NegatedConditionsInUnless
  * Unless blocks should not contain a negated condition
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/negated_conditions_in_unless.ex)

## Refactor.NegatedConditionsWithElse
  * An `if` block with a negated condition should not contain an else block
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/negated_conditions_with_else.ex)

## Refactor.Nesting
  * Code should not be nested more than once inside a function
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/nesting.ex)

## Refactor.UnlessWithElse
  *  An `unless` block should not contain an else block
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/refactor/unless_with_else.ex)

## Warning.IExPry
  * Most calls to the IExPry function are added during debugging sessions
  * This check warns about those calls, because they might have been committed in error
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/iex_pry.ex)

## Warning.IoInspect
  * Most calls to the IoInspect function are added during debugging sessions
  * This check warns about those calls, because they might have been committed in error
  [read more](https://github.com/rrrene/elixir-style-guide)

## Warning.NameRedeclarationByAssignment
  * The names of local variables should not be the same as names of functions or macros in the same module or in `Kernel`.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/name_redeclaration_by_assignment.ex)

## Warning.NameRedeclarationByCase
  * Names assigned to choices in a `case` statement should not be the same as names of functions in the same module or in `Kernel`.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/name_redeclaration_by_case.ex)

## Warning.NameRedeclarationByDef
  * Names assigned to parameters of a named function should not be the same as names of functions in the same module or in `Kernel`.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/name_redeclaration_by_def.ex)

## Warning.NameRedeclarationByFn
  * Names assigned to parameters of an anonymous function should not be the same as names of functions in the same module or in `Kernel`
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/name_redeclaration_by_fn.ex)

## Warning.OperationOnSameValues
  * Operations on the same values always yield the same result are likely the result of a debugging session or mistake.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/operation_on_same_values.ex

## Warning.BoolOperationOnSameValues
  * Boolean operations with identical values on the left and right side are most probably a logical fallacy.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/bool_operation_on_same_values.ex)

## Warning.UnusedEnumOperation
  * With the exception of `Enum.each/2`, the result of a call to the Enum module's functions has to be used.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/unused_enum_operation.ex)

## Warning.UnusedKeywordOperation
  * The result of a call to the Keyword module's functions has to be used.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/unused_keyword_operation.ex)

## Warning.UnusedListOperation
  * The result of a call to the List module's functions has to be used.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/unused_list_operation.ex)

## Warning.UnusedStringOperation
  * The result of a call to the String module's functions has to be used.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/unused_string_operation.ex)

## Warning.UnusedTupleOperation
  * The result of a call to the Tuple module's functions has to be used.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/unused_tuple_operation.ex)

## Warning.OperationWithConstantResult
  * Operations on the same values always yield the same result and therefore make little sense in production code.
  [read more](https://github.com/rrrene/credo/blob/master/lib/credo/check/warning/operation_with_constant_result.ex)
