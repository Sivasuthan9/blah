## Module
```mermaid
flowchart LR
Module -->|str| name
Module -->|JacSource| source
Module -.->|String| doc
Module -->|ElementStmt , String , EmptyToken| body
Module -->|bool| is_imported
Module -.->|Module| impl_mod
Module -.->|Module| test_mod
```

Whole Program node type for Jac Ast.

## GlobalVars
```mermaid
flowchart LR
GlobalVars -.->|Token| access
GlobalVars -->|Assignment| assignments
GlobalVars -->|bool| is_frozen
GlobalVars -.->|String| doc
```

GlobalVars node type for Jac Ast.

## Test
```mermaid
flowchart LR
Test -->|Name , Token| name
Test -->|CodeBlockStmt| body
Test -.->|String| doc
```

Test node type for Jac Ast.

## ModuleCode
```mermaid
flowchart LR
ModuleCode -.->|Name| name
ModuleCode -->|CodeBlockStmt| body
ModuleCode -.->|String| doc
```

Free mod code for Jac Ast.

## PyInlineCode
```mermaid
flowchart LR
PyInlineCode -->|Token| code
PyInlineCode -.->|String| doc
```

Inline Python code node type for Jac Ast.

## Import
```mermaid
flowchart LR
Import -->|Name| lang
Import -->|list - ModulePath| paths
Import -.->|ModuleItem| items
Import -->|bool| is_absorb
Import -.->|String| doc
```

Import node type for Jac Ast.

## ModulePath
```mermaid
flowchart LR
ModulePath -.->|list - Name| path
ModulePath -->|int| level
ModulePath -.->|Name| alias
ModulePath -.->|Module| sub_module
```

ModulePath node type for Jac Ast.

## ModuleItem
```mermaid
flowchart LR
ModuleItem -->|Name| name
ModuleItem -.->|Name| alias
```

ModuleItem node type for Jac Ast.

## Architype
```mermaid
flowchart LR
Architype -->|Name| name
Architype -->|Token| arch_type
Architype -.->|Token| access
Architype -.->|Expr| base_classes
Architype -.->|ArchBlockStmt , ArchDef| body
Architype -.->|String| doc
Architype -.->|String| semstr
Architype -.->|Expr| decorators
```

ObjectArch node type for Jac Ast.

## ArchDef
```mermaid
flowchart LR
ArchDef -->|ArchRefChain| target
ArchDef -->|ArchBlockStmt| body
ArchDef -.->|String| doc
ArchDef -.->|Expr| decorators
ArchDef -.->|Architype| decl_link
```

ArchDef node type for Jac Ast.

## EnumDef
```mermaid
flowchart LR
EnumDef -->|ArchRefChain| target
EnumDef -->|EnumBlockStmt| body
EnumDef -.->|String| doc
EnumDef -.->|Expr| decorators
EnumDef -.->|Enum| decl_link
```

EnumDef node type for Jac Ast.

## Ability
```mermaid
flowchart LR
Ability -->|NameSpec| name_ref
Ability -->|bool| is_func
Ability -->|bool| is_async
Ability -->|bool| is_override
Ability -->|bool| is_static
Ability -->|bool| is_abstract
Ability -.->|Token| access
Ability -.->|FuncSignature , EventSignature| signature
Ability -.->|CodeBlockStmt , AbilityDef| body
Ability -.->|String| semstr
Ability -.->|String| doc
Ability -.->|Expr| decorators
```

Ability node type for Jac Ast.

## AbilityDef
```mermaid
flowchart LR
AbilityDef -->|ArchRefChain| target
AbilityDef -->|FuncSignature , EventSignature| signature
AbilityDef -->|CodeBlockStmt| body
AbilityDef -.->|String| doc
AbilityDef -.->|Expr| decorators
AbilityDef -.->|Ability| decl_link
```

AbilityDef node type for Jac Ast.

## FuncSignature
```mermaid
flowchart LR
FuncSignature -.->|ParamVar| params
FuncSignature -.->|Expr| return_type
FuncSignature -.->|String| semstr
```

FuncSignature node type for Jac Ast.

## EventSignature
```mermaid
flowchart LR
EventSignature -->|Token| event
EventSignature -.->|Expr| arch_tag_info
EventSignature -.->|Expr| return_type
EventSignature -.->|String| semstr
```

EventSignature node type for Jac Ast.

## ArchRef
```mermaid
flowchart LR
ArchRef -->|NameSpec| name_ref
ArchRef -->|Token| arch
```

ArchRef node type for Jac Ast.

## ArchRefChain
```mermaid
flowchart LR
ArchRefChain -->|list - ArchRef| archs
```

Arch ref list node type for Jac Ast.

## ParamVar
```mermaid
flowchart LR
ParamVar -->|Name| name
ParamVar -.->|Token| unpack
ParamVar -->|Expr| type_tag
ParamVar -.->|Expr| value
ParamVar -.->|String| semstr
```

ParamVar node type for Jac Ast.

## ArchHas
```mermaid
flowchart LR
ArchHas -->|bool| is_static
ArchHas -.->|Token| access
ArchHas -->|HasVar| vars
ArchHas -->|bool| is_frozen
ArchHas -.->|String| doc
```

HasStmt node type for Jac Ast.

## HasVar
```mermaid
flowchart LR
HasVar -->|Name| name
HasVar -->|Expr| type_tag
HasVar -.->|Expr| value
HasVar -->|bool| defer
HasVar -.->|String| semstr
```

HasVar node type for Jac Ast.

## TypedCtxBlock
```mermaid
flowchart LR
TypedCtxBlock -->|Expr| type_ctx
TypedCtxBlock -->|CodeBlockStmt| body
```

TypedCtxBlock node type for Jac Ast.

## IfStmt
```mermaid
flowchart LR
IfStmt -->|Expr| condition
IfStmt -->|CodeBlockStmt| body
IfStmt -.->|ElseStmt , ElseIf| else_body
```

IfStmt node type for Jac Ast.

## ElseIf
```mermaid
flowchart LR
ElseIf -->|Expr| condition
ElseIf -->|CodeBlockStmt| body
ElseIf -.->|ElseStmt , ElseIf| else_body
```

ElseIfs node type for Jac Ast.

## ElseStmt
```mermaid
flowchart LR
ElseStmt -->|CodeBlockStmt| body
```

Else node type for Jac Ast.

## ExprStmt
```mermaid
flowchart LR
ExprStmt -->|Expr| expr
ExprStmt -->|bool| in_fstring
```

ExprStmt node type for Jac Ast.

## TryStmt
```mermaid
flowchart LR
TryStmt -->|CodeBlockStmt| body
TryStmt -.->|Except| excepts
TryStmt -.->|ElseStmt| else_body
TryStmt -.->|FinallyStmt| finally_body
```

TryStmt node type for Jac Ast.

## Except
```mermaid
flowchart LR
Except -->|Expr| ex_type
Except -.->|Name| name
Except -->|CodeBlockStmt| body
```

Except node type for Jac Ast.

## FinallyStmt
```mermaid
flowchart LR
FinallyStmt -->|CodeBlockStmt| body
```

FinallyStmt node type for Jac Ast.

## IterForStmt
```mermaid
flowchart LR
IterForStmt -->|Assignment| iter
IterForStmt -->|bool| is_async
IterForStmt -->|Expr| condition
IterForStmt -->|Assignment| count_by
IterForStmt -->|CodeBlockStmt| body
IterForStmt -.->|ElseStmt| else_body
```

IterFor node type for Jac Ast.

## InForStmt
```mermaid
flowchart LR
InForStmt -->|Expr| target
InForStmt -->|bool| is_async
InForStmt -->|Expr| collection
InForStmt -->|CodeBlockStmt| body
InForStmt -.->|ElseStmt| else_body
```

InFor node type for Jac Ast.

## WhileStmt
```mermaid
flowchart LR
WhileStmt -->|Expr| condition
WhileStmt -->|CodeBlockStmt| body
```

WhileStmt node type for Jac Ast.

## WithStmt
```mermaid
flowchart LR
WithStmt -->|bool| is_async
WithStmt -->|ExprAsItem| exprs
WithStmt -->|CodeBlockStmt| body
```

WithStmt node type for Jac Ast.

## ExprAsItem
```mermaid
flowchart LR
ExprAsItem -->|Expr| expr
ExprAsItem -.->|Expr| alias
```

ExprAsItem node type for Jac Ast.

## RaiseStmt
```mermaid
flowchart LR
RaiseStmt -.->|Expr| cause
RaiseStmt -.->|Expr| from_target
```

RaiseStmt node type for Jac Ast.

## AssertStmt
```mermaid
flowchart LR
AssertStmt -->|Expr| condition
AssertStmt -.->|Expr| error_msg
```

AssertStmt node type for Jac Ast.

## CtrlStmt
```mermaid
flowchart LR
CtrlStmt -->|Token| ctrl
```

CtrlStmt node type for Jac Ast.

## DeleteStmt
```mermaid
flowchart LR
DeleteStmt -->|Expr| target
```

DeleteStmt node type for Jac Ast.

## ReportStmt
```mermaid
flowchart LR
ReportStmt -->|Expr| expr
```

ReportStmt node type for Jac Ast.

## ReturnStmt
```mermaid
flowchart LR
ReturnStmt -.->|Expr| expr
```

ReturnStmt node type for Jac Ast.

## IgnoreStmt
```mermaid
flowchart LR
IgnoreStmt -->|Expr| target
```

IgnoreStmt node type for Jac Ast.

## VisitStmt
```mermaid
flowchart LR
VisitStmt -.->|Expr| vis_type
VisitStmt -->|Expr| target
VisitStmt -.->|ElseStmt| else_body
```

VisitStmt node type for Jac Ast.

## RevisitStmt
```mermaid
flowchart LR
RevisitStmt -.->|Expr| hops
RevisitStmt -.->|ElseStmt| else_body
```

ReVisitStmt node type for Jac Ast.

## AwaitExpr
```mermaid
flowchart LR
AwaitExpr -->|Expr| target
```

AwaitStmt node type for Jac Ast.

## GlobalStmt
```mermaid
flowchart LR
GlobalStmt -->|NameSpec| target
```

GlobalStmt node type for Jac Ast.

## NonLocalStmt
```mermaid
flowchart LR
NonLocalStmt -->|NameSpec| target
```

NonlocalStmt node type for Jac Ast.

## Assignment
```mermaid
flowchart LR
Assignment -->|Expr| target
Assignment -.->|Expr , YieldExpr| value
Assignment -.->|Expr| type_tag
Assignment -->|bool| mutable
Assignment -.->|Token| aug_op
```

Assignment node type for Jac Ast.

## BinaryExpr
```mermaid
flowchart LR
BinaryExpr -->|Expr| left
BinaryExpr -->|Expr| right
BinaryExpr -->|Token , DisconnectOp , ConnectOp| op
```

ExprBinary node type for Jac Ast.

## CompareExpr
```mermaid
flowchart LR
CompareExpr -->|Expr| left
CompareExpr -->|list - Expr| rights
CompareExpr -->|list - Token| ops
```

CompareExpr node type for Jac Ast.

## Bool
```mermaid
flowchart LR
Bool -->|str| file_path
Bool -->|str| name
Bool -->|str| value
Bool -->|int| col_start
Bool -->|int| col_end_
Bool -->|int| pos_start
Bool -->|int| pos_end_
```

Bool node type for Jac Ast.

## BoolExpr
```mermaid
flowchart LR
BoolExpr -->|Token| op
BoolExpr -->|list - Expr| values
```

BoolExpr node type for Jac Ast.

## LambdaExpr
```mermaid
flowchart LR
LambdaExpr -->|FuncSignature| signature
LambdaExpr -->|Expr| body
```

ExprLambda node type for Jac Ast.

## UnaryExpr
```mermaid
flowchart LR
UnaryExpr -->|Expr| operand
UnaryExpr -->|Token| op
```

ExprUnary node type for Jac Ast.

## IfElseExpr
```mermaid
flowchart LR
IfElseExpr -->|Expr| condition
IfElseExpr -->|Expr| value
IfElseExpr -->|Expr| else_value
```

ExprIfElse node type for Jac Ast.

## MultiString
```mermaid
flowchart LR
MultiString -->|String , FString| strings
```

ExprMultiString node type for Jac Ast.

## FString
```mermaid
flowchart LR
FString -.->|String , ExprStmt| parts
```

FString node type for Jac Ast.

## ExprList
```mermaid
flowchart LR
ExprList -.->|Expr| values
```

ExprList node type for Jac Ast.

## ListVal
```mermaid
flowchart LR
ListVal -.->|Expr| values
```

ListVal node type for Jac Ast.

## SetVal
```mermaid
flowchart LR
SetVal -.->|Expr| values
```

SetVal node type for Jac Ast.

## TupleVal
```mermaid
flowchart LR
TupleVal -.->|Expr , KWPair| values
```

TupleVal node type for Jac Ast.

## DictVal
```mermaid
flowchart LR
DictVal -->|KVPair| kv_pairs
```

ExprDict node type for Jac Ast.

## KVPair
```mermaid
flowchart LR
KVPair -.->|Expr| key
KVPair -->|Expr| value
```

ExprKVPair node type for Jac Ast.

## KWPair
```mermaid
flowchart LR
KWPair -.->|NameSpec| key
KWPair -->|Expr| value
```

ExprKWPair node type for Jac Ast.

## InnerCompr
```mermaid
flowchart LR
InnerCompr -->|bool| is_async
InnerCompr -->|Expr| target
InnerCompr -->|Expr| collection
InnerCompr -.->|Expr| conditional
```

ListCompr node type for Jac Ast.

## ListCompr
```mermaid
flowchart LR
ListCompr -->|Expr| out_expr
ListCompr -->|list - InnerCompr| compr
```

ListCompr node type for Jac Ast.

## GenCompr
```mermaid
flowchart LR
GenCompr -->|Expr| out_expr
GenCompr -->|list - InnerCompr| compr
```

GenCompr node type for Jac Ast.

## SetCompr
```mermaid
flowchart LR
SetCompr -->|Expr| out_expr
SetCompr -->|list - InnerCompr| compr
```

SetCompr node type for Jac Ast.

## DictCompr
```mermaid
flowchart LR
DictCompr -->|KVPair| kv_pair
DictCompr -->|list - InnerCompr| compr
```

DictCompr node type for Jac Ast.

## AtomTrailer
```mermaid
flowchart LR
AtomTrailer -->|Expr| target
AtomTrailer -->|AtomExpr , Expr| right
AtomTrailer -.->|Token| is_attr
AtomTrailer -->|bool| is_null_ok
```

AtomTrailer node type for Jac Ast.

## AtomUnit
```mermaid
flowchart LR
AtomUnit -->|Expr , YieldExpr| value
AtomUnit -->|bool| is_paren
```

AtomUnit node type for Jac Ast.

## YieldExpr
```mermaid
flowchart LR
YieldExpr -.->|Expr| expr
YieldExpr -->|bool| with_from
```

YieldStmt node type for Jac Ast.

## FuncCall
```mermaid
flowchart LR
FuncCall -->|Expr| target
FuncCall -.->|Expr , KWPair| params
```

FuncCall node type for Jac Ast.

## IndexSlice
```mermaid
flowchart LR
IndexSlice -.->|Expr| start
IndexSlice -.->|Expr| stop
IndexSlice -.->|Expr| step
IndexSlice -->|bool| is_range
```

IndexSlice node type for Jac Ast.

## SpecialVarRef
```mermaid
flowchart LR
SpecialVarRef -->|Token| var
```

HereRef node type for Jac Ast.

## EdgeRefTrailer
```mermaid
flowchart LR
EdgeRefTrailer -->|list - Expr , FilterCompr| chain
EdgeRefTrailer -->|bool| edges_only
```

EdgeRefTrailer node type for Jac Ast.

## EdgeOpRef
```mermaid
flowchart LR
EdgeOpRef -.->|FilterCompr| filter_cond
EdgeOpRef -->|EdgeDir| edge_dir
```

EdgeOpRef node type for Jac Ast.

## DisconnectOp
```mermaid
flowchart LR
DisconnectOp -->|EdgeOpRef| edge_spec
```

DisconnectOpRef node type for Jac Ast.

## ConnectOp
```mermaid
flowchart LR
ConnectOp -.->|Expr| conn_type
ConnectOp -.->|AssignCompr| conn_assign
ConnectOp -->|EdgeDir| edge_dir
```

ConnectOpRef node type for Jac Ast.

## FilterCompr
```mermaid
flowchart LR
FilterCompr -.->|Expr| f_type
FilterCompr -.->|CompareExpr| compares
```

FilterCtx node type for Jac Ast.

## AssignCompr
```mermaid
flowchart LR
AssignCompr -->|KWPair| assigns
```

AssignCtx node type for Jac Ast.

## MatchStmt
```mermaid
flowchart LR
MatchStmt -->|Expr| target
MatchStmt -->|list - MatchCase| cases
```

MatchStmt node type for Jac Ast.

## MatchCase
```mermaid
flowchart LR
MatchCase -->|MatchPattern| pattern
MatchCase -.->|Expr| guard
MatchCase -->|CodeBlockStmt| body
```

MatchCase node type for Jac Ast.

## MatchOr
```mermaid
flowchart LR
MatchOr -->|list - MatchPattern| patterns
```

MatchOr node type for Jac Ast.

## MatchAs
```mermaid
flowchart LR
MatchAs -->|NameSpec| name
MatchAs -.->|MatchPattern| pattern
```

MatchAs node type for Jac Ast.

## MatchValue
```mermaid
flowchart LR
MatchValue -->|Expr| value
```

MatchValue node type for Jac Ast.

## MatchSingleton
```mermaid
flowchart LR
MatchSingleton -->|Bool , Null| value
```

MatchSingleton node type for Jac Ast.

## MatchSequence
```mermaid
flowchart LR
MatchSequence -->|list - MatchPattern| values
```

MatchSequence node type for Jac Ast.

## MatchMapping
```mermaid
flowchart LR
MatchMapping -->|list - MatchKVPair , MatchStar| values
```

MatchMapping node type for Jac Ast.

## MatchKVPair
```mermaid
flowchart LR
MatchKVPair -->|MatchPattern , NameSpec| key
MatchKVPair -->|MatchPattern| value
```

MatchKVPair node type for Jac Ast.

## MatchStar
```mermaid
flowchart LR
MatchStar -->|NameSpec| name
MatchStar -->|bool| is_list
```

MatchStar node type for Jac Ast.

## MatchArch
```mermaid
flowchart LR
MatchArch -->|NameSpec| name
MatchArch -.->|MatchPattern| arg_patterns
MatchArch -.->|MatchKVPair| kw_patterns
```

MatchClass node type for Jac Ast.

## Token
```mermaid
flowchart LR
Token -->|str| file_path
Token -->|str| name
Token -->|str| value
Token -->|int| col_start
Token -->|int| col_end_
Token -->|int| pos_start
Token -->|int| pos_end_
```

Token node type for Jac Ast.

## BuiltinType
```mermaid
flowchart LR
BuiltinType -->|str| file_path
BuiltinType -->|str| name
BuiltinType -->|str| value
BuiltinType -->|int| col_start
BuiltinType -->|int| col_end_
BuiltinType -->|int| pos_start
BuiltinType -->|int| pos_end_
BuiltinType -->|bool| is_enum_singleton
BuiltinType -->|bool| is_kwesc
```

Type node type for Jac Ast.

## Float
```mermaid
flowchart LR
Float -->|str| file_path
Float -->|str| name
Float -->|str| value
Float -->|int| col_start
Float -->|int| col_end_
Float -->|int| pos_start
Float -->|int| pos_end_
```

Float node type for Jac Ast.

## Int
```mermaid
flowchart LR
Int -->|str| file_path
Int -->|str| name
Int -->|str| value
Int -->|int| col_start
Int -->|int| col_end_
Int -->|int| pos_start
Int -->|int| pos_end_
```

Int node type for Jac Ast.

## String
```mermaid
flowchart LR
String -->|str| file_path
String -->|str| name
String -->|str| value
String -->|int| col_start
String -->|int| col_end_
String -->|int| pos_start
String -->|int| pos_end_
```

String node type for Jac Ast.

## Null
```mermaid
flowchart LR
Null -->|str| file_path
Null -->|str| name
Null -->|str| value
Null -->|int| col_start
Null -->|int| col_end_
Null -->|int| pos_start
Null -->|int| pos_end_
```

Semicolon node type for Jac Ast.

## Ellipsis
```mermaid
flowchart LR
Ellipsis -->|str| file_path
Ellipsis -->|str| name
Ellipsis -->|str| value
Ellipsis -->|int| col_start
Ellipsis -->|int| col_end_
Ellipsis -->|int| pos_start
Ellipsis -->|int| pos_end_
```

Ellipsis node type for Jac Ast.

## Semi
```mermaid
flowchart LR
Semi -->|str| file_path
Semi -->|str| name
Semi -->|str| value
Semi -->|int| col_start
Semi -->|int| col_end_
Semi -->|int| pos_start
Semi -->|int| pos_end_
```

Semicolon node type for Jac Ast.

## CommentToken
```mermaid
flowchart LR
CommentToken -->|str| file_path
CommentToken -->|str| name
CommentToken -->|str| value
CommentToken -->|int| col_start
CommentToken -->|int| col_end_
CommentToken -->|int| pos_start
CommentToken -->|int| pos_end_
CommentToken -->|bool| is_inline
```

CommentToken node type for Jac Ast.
