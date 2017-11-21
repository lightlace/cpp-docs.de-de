---
title: 'Vorgehensweise: Abrufen des lokalen Computernamens (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- computer name, retrieving
- machine name, retrieving
- computer name
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0957ff70d5163c142282a15ac597de5504537636
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-retrieve-the-local-machine-name-ccli"></a>Gewusst wie: Abrufen des lokalen Computernamens (C++/CLI)
Das folgende Codebeispiel veranschaulicht das Abrufen der Namen des lokalen Computers (in einem Netzwerk wird der Name des Computers, wie er angezeigt). Sie können dies bewerkstelligen, durch Abrufen der <xref:System.Environment.MachineName%2A> Zeichenfolge, die in definiert ist die <xref:System.Environment> Namespace.  
  
## <a name="example"></a>Beispiel  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Vorgänge (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)