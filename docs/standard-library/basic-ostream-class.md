---
title: "basic_ostream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ostream"
  - "std.basic_ostream"
  - "ostream/std::basic_ostream"
  - "basic_ostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostream-Klasse"
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_ostream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Vorlagenklasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer mit Elementen des Typs **Elem** steuert, der auch als [char\_type](../Topic/basic_ios::char_type.md) bekannt ist, und dessen Zeichenmerkmale von der Klasse **Tr** bestimmt werden, die auch als [traits\_type](../Topic/basic_ios::traits_type.md) bekannt ist.  
  
## Syntax  
  
```  
  
template <class   
_Elem  
, class   
_Tr  
 = char  
_  
traits<Elem> >  
   class basic  
_  
ostream  
       : virtual public basic  
_  
ios<  
_Elem  
,   
_Tr  
>  
  
```  
  
#### Parameter  
 `_Elem`  
 Ein `char_type`.  
  
 `_Tr`  
 Der `traits_type` eines Zeichens.  
  
## Hinweise  
 Die meisten der Memberfunktionen, die [operator\<\<](../Topic/basic_ostream::operator%3C%3C.md) überladen, sind Funktionen für formatierte Ausgabe. Sie entsprechen dem folgenden Muster:  
  
```  
iostate state = goodbit;  
const sentry ok( *this );  
if ( ok )  
   {try  
      {<convert and insert elements  
      accumulate flags in state> }  
   catch ( ... )  
      {try  
        {setstate( badbit ); }  
      catch ( ... )  
        {}  
      if ( ( exceptions( ) & badbit ) != 0 )  
        throw; }}  
width( 0 );    // Except for operator<<(Elem)  
setstate( state );  
return ( *this );  
```  
  
 Zwei weitere Memberfunktionen sind Funktionen für unformatierte Ausgabe. Sie entsprechen dem folgenden Muster:  
  
```  
iostate state = goodbit;  
const sentry ok( *this );  
if ( !ok )  
   state |= badbit;  
else  
   {try  
      {<obtain and insert elements  
      accumulate flags in state> }  
   catch ( ... )  
      {try  
         {setstate( badbit ); }  
      catch ( ... )  
         {}  
      if ( ( exceptions( ) & badbit ) != 0 )  
         throw; }}  
setstate( state );  
return ( *this );  
```  
  
 Beide Gruppen von Funktionen rufen [setstate](../Topic/basic_ios::setstate.md)**\(badbit\)** auf, wenn sie beim Einfügen von Elementen einen Fehler feststellen.  
  
 Ein aus der Klasse "basic\_istream \<**ElemTr**\>" abgeleitetes Objekt speichert nur ein virtuelles öffentliches Basisobjekt der Klasse[basic\_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr\>**.  
  
## Beispiel  
 Siehe das Beispiel für [basic\_ofstream\-Klasse](../standard-library/basic-ofstream-class.md) Weitere Informationen zu Ausgabestreams.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_ostream](../Topic/basic_ostream::basic_ostream.md)|Erstellt ein `basic_ostream`\-Objekt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[flush](../Topic/basic_ostream::flush.md)|Leert den Puffer.|  
|[put](../Topic/basic_ostream::put.md)|Schreibt ein Zeichen in einen Stream.|  
|[seekp](../Topic/basic_ostream::seekp.md)|Setzt die Position im Ausgabestream zurück.|  
|[sentry](../Topic/basic_ostream::sentry.md)|Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die Funktionen für formatierte Ausgabe und für unformatierte Ausgabe strukturiert.|  
|[swap](../Topic/basic_ostream::operator=.md)|Tauscht die Werte dieses `basic_ostream`\-Objekts gegen die Werte des bereitgestellten `basic_ostream`\-Objekts aus.|  
|[tellp](../Topic/basic_ostream::tellp.md)|Meldet die Position im Ausgabestream.|  
|[Schreiben](../Topic/basic_ostream::write.md)|Schreibt Zeichen in einen Stream.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ostream::operator=.md)|Weist diesem Objekt den Wert des bereitgestellten `basic_ostream`\-Objektparameters zu.|  
|[Operator \<\<](../Topic/basic_ostream::operator%3C%3C.md)|Schreibt in den Stream.|  
  
## Anforderungen  
 **Header:** \<ostream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)