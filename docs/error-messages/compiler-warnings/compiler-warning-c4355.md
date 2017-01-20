---
title: "Compilerwarnung C4355"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4355"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4355"
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4355
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"this": Wird in der Basisliste für den Memberinitialisierer verwendet  
  
 Der **this**\-Zeiger ist nur in nicht statischen Memberfunktionen gültig.  Er kann in der Initialisiererliste für eine Basisklasse nicht verwendet werden.  
  
 Die Konstruktoren für Basisklassen und Klassenmember werden vor dem **this**\-Konstruktor aufgerufen.  Tatsächlich wurde ein Zeiger auf ein nicht erstelltes Objekt an einen anderen Konstruktor übergeben.  Wenn diese anderen Konstruktoren auf Member zugreifen oder Memberfunktionen für this aufrufen, ist das Ergebnis nicht definiert.  Sie sollten den **this**\-Zeiger nicht verwenden, bis die Erstellung vollständig abgeschlossen ist.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4355 generiert:  
  
```  
// C4355.cpp  
// compile with: /w14355 /c  
#include <tchar.h>  
  
class CDerived;  
class CBase {  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function() = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase {  
public:  
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor  
   virtual void function() {};  
};  
  
CBase::~CBase() {  
   m_pDerived -> function();  
}  
  
int main() {  
   CDerived myDerived;  
}  
```