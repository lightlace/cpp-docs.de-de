---
title: "public (C++)"
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
  - "public"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "public-Schlüsselwort [C++]"
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# public (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## Hinweise  
 Wenn das **public**\-Schlüsselwort einer Liste von Klassenmembern vorangestellt ist, gibt es an, dass auf diese Member aus jeder Funktion zugegriffen werden kann.  Dies gilt für alle Member, die bis zum nächsten Zugriffsspezifizierer oder am Ende der Klasse deklariert werden.  
  
 Wenn das **public**\-Schlüsselwort dem Namen einer Basisklasse vorangestellt ist, gibt es an, dass die öffentlichen und geschützten Member der Basisklasse öffentliche bzw. geschützte Member der abgeleiteten Klasse sind.  
  
 Der Standardzugriff von Membern einer Klasse ist privat.  Der Standardzugriff der Member in einer Struktur oder Union ist öffentlich.  
  
 Der Standardzugriff einer Basisklasse ist bei Klassen privat und bei Strukturen öffentlich.  Unions können keine Basisklassen aufweisen.  
  
 Weitere Informationen finden Sie unter [privat](../cpp/private-cpp.md), [geschützt](../cpp/protected-cpp.md), [friend](../cpp/friend-cpp.md) und der Memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md).  
  
## "\/clr"\-spezifisch  
 In CLR\-Typen können die C\+\+\-Schlüsselwörter für Zugriffsspezifizierer \(**public**, `private` und `protected`\) die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen.  Weitere Informationen finden Sie unter [Typ\- und Membersichtbarkeit](../misc/type-and-member-visibility.md).  
  
> [!NOTE]
>  Dateien, die mit [\/LN](../build/reference/ln-create-msil-module.md) kompiliert werden, werden durch dieses Verhalten nicht beeinflusst.  In diesem Fall werden alle verwalteten Klassen \(entweder "public" oder "private"\) angezeigt.  
  
## "\/clr"\-spezifisch – Ende  
  
## Beispiel  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## Siehe auch  
 [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)