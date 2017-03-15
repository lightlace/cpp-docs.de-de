---
title: "private (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "private_cpp"
  - "private"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "private-Schlüsselwort [C++]"
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# private (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## Hinweise  
 Wenn das `private`\-Schlüsselwort einer Liste von Klassenmembern vorangestellt ist, gibt es an, dass auf diese Member nur von Memberfunktionen und Friends der Klasse zugegriffen werden kann.  Dies gilt für alle Member, die bis zum nächsten Zugriffsspezifizierer oder am Ende der Klasse deklariert werden.  
  
 Wenn das `private`\-Schlüsselwort dem Namen einer Basisklasse vorangestellt ist, gibt es an, dass die öffentlichen und geschützten Member der Basisklasse private Member der abgeleiteten Klasse sind.  
  
 Der Standardzugriff von Membern einer Klasse ist privat.  Der Standardzugriff der Member in einer Struktur oder Union ist öffentlich.  
  
 Der Standardzugriff einer Basisklasse ist bei Klassen privat und bei Strukturen öffentlich.  Unions können keine Basisklassen aufweisen.  
  
 Weitere Informationen finden Sie unter [friend](../cpp/friend-cpp.md), [öffentlich](../cpp/public-cpp.md), [geschützt](../cpp/protected-cpp.md) und in der Memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md).  
  
## "\/clr"\-spezifisch  
 In CLR\-Typen können die C\+\+\-Schlüsselwörter für Zugriffsspezifizierer \(**public**, `private` und `protected`\) die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen.  Weitere Informationen finden Sie unter [Typ\- und Membersichtbarkeit](../misc/type-and-member-visibility.md).  
  
> [!NOTE]
>  Dateien, die mit [\/LN](../build/reference/ln-create-msil-module.md) kompiliert werden, werden durch dieses Verhalten nicht beeinflusst.  In diesem Fall werden alle verwalteten Klassen \(entweder "public" oder "private"\) angezeigt.  
  
## "\/clr"\-spezifisch – Ende  
  
## Beispiel  
  
```  
// keyword_private.cpp  
class BaseClass {  
public:  
   // privMem accessible from member function  
   int pubFunc() { return privMem; }  
private:  
   void privMem;  
};  
  
class DerivedClass : public BaseClass {  
public:  
   void usePrivate( int i )  
      { privMem = i; }   // C2248: privMem not accessible  
                         // from derived class  
};  
  
class DerivedClass2 : private BaseClass {  
public:  
   // pubFunc() accessible from derived class  
   int usePublic() { return pubFunc(); }  
};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   DerivedClass2 aDerived2;  
   aBase.privMem = 1;     // C2248: privMem not accessible  
   aDerived.privMem = 1;  // C2248: privMem not accessible  
                          //    in derived class  
   aDerived2.pubFunc();   // C2247: pubFunc() is private in  
                          //    derived class  
}  
```  
  
## Siehe auch  
 [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)