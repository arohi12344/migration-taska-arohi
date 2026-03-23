---
name: Application Code Migration
description: Systematic approach to migrating legacy code to modern tech stacks while preserving business logic and ensuring zero functionality loss
type: workflow
difficulty: advanced
domains:
  - code-migration
  - legacy-systems
  - refactoring
  - modernization
keywords:
  - migration
  - legacy-code
  - modernization
  - code-translation
  - business-logic-preservation
  - technical-debt
minExperience: intermediate
---

# Application Code Migration Skill

## Purpose

Systematically migrate legacy code from obsolete languages/frameworks to modern tech stacks while maintaining 100% business logic integrity. This skill ensures meticulous translation without missing code sections, proper handling of edge cases, and quality validation at each step.

## When to Use This Skill

- Converting code from legacy languages (COBOL, TELON, FORTRAN, VB6, etc.) to modern languages (Java, Python, C#, TypeScript, etc.)
- Modernizing applications from outdated frameworks to current standards
- Preserving critical business logic during technology transitions
- Maintaining data integrity and API contracts during migration
- Handling complex domain-specific code patterns

## Core Principles

1. **Business Logic Preservation** — Never modify the core business logic unless explicitly instructed; maintain semantic equivalence
2. **Zero Loss of Functionality** — Account for every code construct; use systematic analysis to ensure complete coverage
3. **Incremental Validation** — Migrate in logical units; validate each section before proceeding
4. **Pattern Recognition** — Identify recurring code patterns and translate them consistently
5. **Legacy Quirk Handling** — Understand and properly translate language-specific behaviors and edge cases
6. **Traceability** — Maintain clear mapping between source and migrated code for verification
7. **Quality Gates** — Implement critical checks at each phase to catch issues early

## Pre-Migration Analysis Phase

### 1. Codebase Assessment
**Objective:** Understand the complete scope, structure, and complexity

- [ ] **Inventory all source files** — Catalog files, file sizes, line counts, and relationships
- [ ] **Identify code layers** — Separate UI, business logic, data access, utilities, configuration
- [ ] **Map dependencies** — Document internal and external module dependencies
- [ ] **Classify code patterns** — Identify recurring structures: CRUD operations, data transformations, control flow patterns
- [ ] **Extract metadata** — Capture timestamps, comments, author markers (e.g., `JA010`, `MD15`) that indicate change history
- [ ] **Document language-specific features** — Note idioms, language constructs, or framework features unique to source language
- [ ] **Create a migration map** — Build a reference document showing source construct → target construct mapping

**Deliverable:** Comprehensive codebase analysis document with file inventory, dependency graph, and pattern catalog

### 2. Technology Target Validation
**Objective:** Ensure target tech stack can support migrated code

- [ ] **Feature coverage** — Verify target language/framework supports required functionality
- [ ] **Data type mapping** — Create conversion table for source → target data types (e.g., COBOL USAGE → Java types)
- [ ] **Library equivalents** — Identify target libraries that replace source framework functions
- [ ] **Performance implications** — Flag any known performance differences or bottlenecks
- [ ] **Compliance requirements** — Ensure target stack supports regulatory or architectural constraints

**Deliverable:** Technology compatibility matrix and data type mapping reference

### 3. Business Logic Extraction
**Objective:** Extract and document the pure business logic independent of language

- [ ] **Identify business rules** — Extract all conditional logic, calculations, validations
- [ ] **Document state management** — Chart how data flows and state changes through execution
- [ ] **Capture edge cases** — Note special conditions, error handling, boundary cases
- [ ] **Extract algorithms** — Isolate and document complex algorithms separately
- [ ] **Create pseudocode** — Write language-agnostic pseudocode for complex sections

**Deliverable:** Business logic documentation, pseudocode reference, and decision trees

---

## Migration Execution Phase

### 4. Systematic Code Translation
**Objective:** Methodically translate source code to target language while maintaining behavior

#### Translation Strategy
Choose appropriate approach based on code type:

**A. Pattern-Based Translation** (For repetitive structures)
- Identify common patterns in source code
- Create translation templates for each pattern
- Apply templates consistently across codebase
- Document any pattern variations that required custom handling

**B. Modular Translation** (For layered code)
- Start with lowest-level modules (utilities, data structures)
- Progress to business logic layer
- Finish with UI/integration layer
- This ensures dependencies are satisfied in order

**C. Parallel Translation** (For independent sections)
- Identify truly independent code sections
- Translate in parallel when possible
- Reduces overall migration time
- Requires intermediate validation checkpoints

#### Translation Process

For each code section:

```
1. Source Analysis
   ├─ Identify all variables, functions, methods
   ├─ Map variable types to target type system
   ├─ Extract control flow structures
   └─ Note any language-specific idioms

2. Skeleton Creation
   ├─ Create target function/class structure
   ├─ Define all parameters and return types
   ├─ Add placeholder implementations
   └─ Preserve original naming conventions (initially)

3. Body Translation
   ├─ Translate each logical statement/block
   ├─ Preserve execution semantics exactly
   ├─ Handle language differences in operators, string handling, etc.
   ├─ Translate error handling appropriately
   └─ Add comments noting non-obvious translations

4. Idiom Modernization (Optional)
   ├─ Only after ensuring semantic equivalence
   ├─ Update naming to target language conventions
   ├─ Leverage target language idioms and libraries
   ├─ Improve readability where possible
   └─ Maintain semantic equivalence

5. Inline Documentation
   └─ Add comments explaining any non-obvious translations
      particularly for business logic that was implicit in source
```

#### Language-Specific Handling

**Data Type Translation**
- Account for precision differences (float vs decimal)
- Handle string encoding and length differences
- Map numeric types (COBOL COMP vs Java int/long)
- Translate date/time types and formats
- Handle special types (PICTURE clauses, USAGE keywords, etc.)

**Control Flow**
- COBOL PERFORM → Loop/Recursion (context-dependent)
- GOTO/label jumps → Structured control flow (function extraction)
- EVALUATE/CASE → Switch statements
- Working storage → Class/method variables with appropriate scope

**I/O and File Access**
- COBOL file operations → Target platform file APIs
- Record layouts → Data structures/classes
- Database operations → ORM or query libraries
- Screen/form operations → UI framework equivalents

**Numeric and String Operations**
- COBOL string intrinsics → Target string library equivalents
- Numeric precision handling → Appropriate type selection
- Fixed-length vs variable-length strings → Platform conventions
- EBCDIC vs ASCII encoding → Proper character set handling

### 5. Incremental Validation
**Objective:** Catch and correct issues early in the translation process

After translating each module/section:

- [ ] **Syntax validation** — Code compiles without errors
- [ ] **Unit test verification** — Original tests pass (if available)
- [ ] **Mock integration** — Verify interfaces with adjacent modules
- [ ] **Variable trace** — Manually trace variable assignments through key code paths
- [ ] **Edge case spot check** — Verify boundary conditions execute correctly
- [ ] **Type safety** — Ensure no implicit type conversions or coercions
- [ ] **Resource cleanup** — Verify proper file/memory cleanup (if applicable)

**Stop and correct** — Do not proceed until validation passes

### 6. Integration and System Testing
**Objective:** Verify entire system works correctly

#### Data Integrity Testing
- [ ] **Sample data translation** — Execute end-to-end with test data from original system
- [ ] **Calculation verification** — Manually verify calculations against source system
- [ ] **State verification** — Confirm all state changes match original behavior
- [ ] **Boundary testing** — Test with edge case data (max/min values, empty sets, special characters)
- [ ] **Error path testing** — Trigger all error conditions and verify handling

#### Behavior Equivalence Testing
- [ ] **Functional parity** — System produces identical output for same inputs
- [ ] **Performance characterization** — Document any performance differences
- [ ] **Regression testing** — Run full test suite if available
- [ ] **Smoke testing** — Basic happy-path tests pass
- [ ] **Compatibility testing** — Interfaces with external systems work correctly

---

## Quality Assurance Phase

### 7. Completeness Verification
**Objective:** Confirm 100% of source code has been accounted for

- [ ] **Code coverage analysis** — All source lines translated or deliberately excluded
- [ ] **Comment/metadata migration** — Important comments preserved in target code
- [ ] **Configuration migration** — All configuration parameters transferred
- [ ] **Constants/literals** — All hardcoded values accounted for
- [ ] **Exception handling** — All error cases handled appropriately
- [ ] **Special flags review** — All change markers (e.g., `JA010`, `MD15`) reviewed and translated

**Deliverable:** Coverage report with line-by-line mapping and any discrepancies resolved

### 8. Business Logic Validation
**Objective:** Verify business rules are preserved exactly

- [ ] **Rule verification** — Each extracted business rule present in migrated code
- [ ] **Calculation spot-check** — 10-15 sample calculations produce identical results
- [ ] **Decision point testing** — All conditional branches behave identically
- [ ] **Data consistency** — Constraints and validations are replicated
- [ ] **Workflow correctness** — Process flows and sequences are preserved

**Create test cases** for critical business logic to demonstrate equivalence

### 9. Code Quality and Modernization Review
**Objective:** Ensure target code is maintainable while preserving functionality

- [ ] **Naming conventions** — Variables and functions follow target language standards
- [ ] **Code organization** — logical structure and modularity
- [ ] **Documentation** — Complex sections well-commented
- [ ] **Error handling** — Appropriate for target platform
- [ ] **Security** — No introduction of security vulnerabilities during translation
- [ ] **Performance** — No unnecessary inefficiencies
- [ ] **Dependencies** — All required libraries identified and documented

**Note:** If code needs modernization (refactoring), do that in separate phase post-validation

### 10. Documentation and Handoff
**Objective:** Create comprehensive migration documentation

- [ ] **Migration report** — Overview of scope, approach, and results
- [ ] **Code mapping document** — Source file/function → Target file/function mapping
- [ ] **Known differences** — Any behavioral differences between source and target (if any)
- [ ] **Configuration guide** — How to configure and deploy migrated system
- [ ] **Testing summary** — Key tests, results, and coverage metrics
- [ ] **Lessons learned** — Patterns discovered, gotchas encountered, recommendations

---

## Common Pitfalls and How to Avoid Them

| Pitfall | Impact | Prevention |
|---------|--------|-----------|
| Mistranslating domain-specific constructs | Wrong business logic | Extract and document domain semantics before translation |
| Inconsistent pattern translation | Subtle bugs | Identify patterns first; create and reuse templates |
| Missing edge cases | Incomplete functionality | Systematically trace variable usage and state changes |
| Losing implicit business rules | Logic gaps | Carefully review comments and variable naming in source |
| Scope/lifetime issues | Memory leaks, state bugs | Map source scoping to target language carefully |
| Numeric precision loss | Calculation errors | Explicitly map numeric types; test with known values |
| String handling differences | Data corruption | Handle encoding, length, and type conversions explicitly |
| Missing error handling | Silent failures | Translate all error paths; test error conditions |

---

## Tools and Techniques

### Code Analysis Tools
- **Code structure visualization** — Map file dependencies and module relationships
- **Pattern detection** — Use regex or AST analysis to find recurring code patterns
- **Diff tools** — Compare original and migrated code side-by-side
- **Coverage tools** — Identify untranslated code sections
- **Test generation** — Create automated tests for business logic validation

### Validation Techniques
- **Trace tables** — Manually trace variable values through key code paths
- **Pseudocode comparison** — Compare pseudocode representations of source and target
- **Property-based testing** — Verify invariants are maintained in migrated code
- **Regression testing** — Run existing tests against migrated code
- **Sample data testing** — Execute with real business data examples

---

## Success Criteria

Migration is successful when:

✅ All source code sections have been translated or explicitly documented as intentionally excluded  
✅ Migrated code compiles without errors and warnings in target language  
✅ All business logic behaves identically to source system  
✅ Sample calculations and processes produce identical output  
✅ Edge cases and error conditions handled appropriately  
✅ System integrates correctly with external dependencies  
✅ Code is maintainable and follows target language conventions  
✅ Comprehensive documentation enables support/maintenance  
✅ Test coverage validates behavior equivalence  

---

## Workflow Summary

```
Pre-Migration          Migration              QA & Validation      Delivery
┌──────────────────┐  ┌─────────────────┐   ┌──────────────────┐  ┌──────┐
│ Codebase         │→ │ Systematic      │ → │ Completeness     │→ │Final │
│ Assessment       │  │ Code            │   │ Verification     │  │QA    │
├──────────────────┤  │ Translation     │   ├──────────────────┤  ├──────┤
│ Technology       │  └─────────────────┘   │ Business Logic   │  │Docs &│
│ Validation       │        ↓                │ Validation       │  │Release
├──────────────────┤  ┌─────────────────┐   ├──────────────────┤  └──────┘
│ Business Logic   │→ │ Incremental     │ → │ Code Quality     │
│ Extraction       │  │ Validation      │   │ Review           │
└──────────────────┘  └─────────────────┘   └──────────────────┘
```

---

## Related Prompts to Use This Skill

- "Migrate this COBOL program to Java following the migration skill workflow"
- "Analyze this legacy code and extract business logic before migration"
- "Validate that the migrated code preserves all original functionality"
- "Create a migration map for translating TELON constructs to modern patterns"
- "Test the migrated system against sample business data; verify calculation accuracy"

---

## Customization Tips

- **Adjust for language pairs** — Customize data type mappings and idiom handling based on specific source→target language combination
- **Regulatory compliance** — Add compliance-specific validation steps if required (e.g., financial, healthcare)
- **Performance optimization** — Include performance profiling/optimization phase if legacy system had known bottlenecks
- **Large-scale migrations** — Add staging/phased rollout validation if migrating system still in production
