---
title: 'Vorgehensweise: Abrufen des aktuellen Benutzernamens (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1532647327c039994a1d09ee8b7eacc2c341f88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-retrieve-the-current-username-ccli"></a>Gewusst wie: Abrufen des aktuellen Benutzernamens (C++/CLI)
Das folgende Codebeispiel veranschaulicht das Abrufen des aktuellen Benutzernamens (der Name des Benutzers bei Windows angemeldet ist). Der Name befindet sich in der <xref:System.Environment.UserName%2A> Zeichenfolge, die in definiert ist die <xref:System.Environment> Namespace.  
  
## <a name="example"></a>Beispiel  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Vorgänge (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)