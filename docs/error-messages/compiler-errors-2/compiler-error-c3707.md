---
title: "Compilerfehler C3707 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3707"
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': dispinterface\-Methode muss eine 'dispid' haben  
  
 Wenn Sie eine `dispinterface`\-Methode verwenden, müssen Sie ihr eine `dispid` zuweisen.  Weisen Sie zur Behebung des Fehlers eine `dispid` der `dispinterface`\-Methode zu, beispielsweise, indem Sie das `id`\-Attribut in der Methode im folgenden Beispiel auskommentieren.  Weitere Informationen finden Sie unter den Ausführungen zu den Attributen [dispinterface](../../windows/dispinterface.md) und [id](../../windows/id.md).  
  
 Im folgenden Beispiel wird C3707 generiert:  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```