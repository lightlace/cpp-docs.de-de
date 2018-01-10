---
title: 'Vorgehensweise: Ermitteln des interaktiven Zustands (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a2cb3ffb8e0bfd8eba04555286894b6f1e58cfd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-determine-the-user-interactive-state-ccli"></a>Gewusst wie: Ermitteln des interaktiven Zustands (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie zu bestimmen, ob Code in einem interaktiven Kontext ausgeführt wird. Wenn <xref:System.Environment.UserInteractive%2A> ist "false", und klicken Sie dann der Code als ein Dienstprozess ausgeführt wird oder aus in einer Web-Anwendung, in diesem Fall Sie nicht versuchen sollten, mit dem Benutzer interagieren.  
  
## <a name="example"></a>Beispiel  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Vorgänge (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)