---
title: Private (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: private_cpp
dev_langs: C++
helpviewer_keywords: private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: baa3a23eacc8428bcbeb6ee5a88a835ff193ee02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="private-c"></a>private (C++)
## <a name="syntax"></a>Syntax  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn das `private`-Schlüsselwort einer Liste von Klassenmembern vorangestellt ist, gibt es an, dass auf diese Member nur von Memberfunktionen und Friends der Klasse zugegriffen werden kann. Dies gilt für alle Member, die bis zum nächsten Zugriffsspezifizierer oder am Ende der Klasse deklariert werden.  
  
 Wenn das `private`-Schlüsselwort dem Namen einer Basisklasse vorangestellt ist, gibt es an, dass die öffentlichen und geschützten Member der Basisklasse private Member der abgeleiteten Klasse sind.  
  
 Der Standardzugriff von Membern einer Klasse ist privat. Der Standardzugriff der Member in einer Struktur oder Union ist öffentlich.  
  
 Der Standardzugriff einer Basisklasse ist bei Klassen privat und bei Strukturen öffentlich. Unions können keine Basisklassen aufweisen.  
  
 Weitere Informationen finden Sie unter ["Friend"](../cpp/friend-cpp.md), [öffentlichen](../cpp/public-cpp.md), [geschützt](../cpp/protected-cpp.md), und der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>"/clr"-spezifisch  
 In CLR-Typen, die C++ Schlüsselwörter für Zugriffsspezifizierer zugreifen (**öffentlichen**, `private`, und `protected`) kann die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen. Weitere Informationen finden Sie unter [Memberzugriffssteuerung](member-access-control-cpp.md).  
  
> [!NOTE]
>  Dateien mit kompiliert [/ln](../build/reference/ln-create-msil-module.md) nicht durch dieses Verhalten beeinträchtigt werden. In diesem Fall werden alle verwalteten Klassen (entweder "public" oder "private") angezeigt.  
  
## <a name="end-clr-specific"></a>"/clr"-spezifisch – Ende  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)