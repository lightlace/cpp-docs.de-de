---
title: 'Vorgehensweise: Abrufen des aktuellen Benutzernamens (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48b48b2d6ad84a85ca100c45a87f5d5037de684f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127821"
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