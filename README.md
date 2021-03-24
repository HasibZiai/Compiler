# Compiler

This project is a simple compiler that uses syntax rules (seen below) to parse and better understand compilation techniques. 

Syntax Rules

<Rat20F>  ::=  <Opt Function Definitions>  
                         %%  <Opt Declaration List> <Statement List>    
<Opt Function Definitions> ::= <Function Definitions> | <Empty>
<Function Definitions>  ::= <Function> < Function Definitions Prime>
<Function Definitions Prime>  ::= <Function Definitions> | <Empty>  
<Function> ::=  @  <Identifier>  (<Opt Parameter List> )   <Opt Declaration List>  <Body>
<Opt Parameter List> ::=  <Parameter List>   |  <Empty>
<Parameter List>  ::=  <Parameter> <Parameter List Prime>
<Parameter List Prime>  ::= , <Parameter List> | <Empty>
<Parameter> ::=  <IDs > : <Qualifier> 
<Qualifier> ::= integer   |  boolean  |  floating
<Body>  ::=  {  < Statement List>  }
<Opt Declaration List> ::= <Declaration List>   | <Empty>
<Declaration List>  := <Declaration> ;  <Declaration List Prime>
<Declaration List Prime>  := <Declaration List> | <Empty>
<Declaration> ::=  <Qualifier > <IDs>                   
<IDs> ::=  <Identifier> <IDs Prime>
<IDs Prime> ::=  , <IDs> | <Empty>
<Statement List> ::=  <Statement> <Statement List Prime>
<Statement List Prime> ::=  <Statement List> | <Empty>
<Statement> ::=  <Compound> | <Assign> | <If> |  <Return> | <Write> | <Read> | <While> 
<Compound> ::= {  <Statement List>  } 
<Assign> ::=   <Identifier> := <Expression> ;
<If> ::=     if  ( <Condition>  ) <Statement> <If Prime> 
<If Prime> ::=  fi | else <Statement> fi  
<Return> ::=  return <Return Prime>
<Return Prime> ::=  ; |  <Expression> ;
<Write> ::=   write ( <Expression>);
<Read> ::=    read ( <IDs> );
<While> ::= while ( <Condition>  )  <Statement> 
<Condition> ::= <Expression>  <Relop>   <Expression>
<Relop> ::=   = |  /=  |   >   | <   |  =>   | <=            
<Expression>  ::= <Term> <Expression Prime>
<Expression Prime>  ::= + <Term> <Expression Prime>  |  - <Term> <Expression Prime> | <Empty>
<Term>    ::=  <Factor> <Term Prime>
<Term Prime>    ::=  * <Factor> <Term Prime> |  / <Factor> <Term Prime> |  <Empty>
<Factor> ::= - <Primary>   | <Primary>
<Primary> ::= <Identifier> <Primary Prime> | <Integer> | ( <Expression> ) |  <Real>  | true | false        
<Primary Prime> ::= [<IDs>] | <Empty>                
<Empty>   ::= 
