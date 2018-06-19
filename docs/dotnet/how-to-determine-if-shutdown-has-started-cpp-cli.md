---
title: 'Vorgehensweise: bestimmen, ob das Herunterfahren begonnen hat (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bbcc2b1efa54808b25238bde4de3dcc21d2ba687
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137701"
---
# <a name="how-to-determine-if-shutdown-has-started-ccli"></a>Gewusst wie: Ermitteln, ob das Herunterfahren begonnen hat (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie zu bestimmen, ob die Anwendung oder .NET Framework gerade beendet wird. Dies ist nützlich für den Zugriff auf statische Elemente in .NET Framework, da während des Herunterfahrens können diese Konstrukte durch das System beendet werden und können nicht zuverlässig verwendet werden kann. Durch Überprüfen der <xref:System.Environment.HasShutdownStarted%2A> Eigenschaft zunächst können Sie potenzielle Fehler vermeiden, indem Sie nicht auf diese Elemente zugreifen.  
  
## <a name="example"></a>Beispiel  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Vorgänge (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)