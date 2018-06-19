---
title: 'Vorgehensweise: Abrufen des lokalen Computernamens (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- computer name, retrieving
- machine name, retrieving
- computer name
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f02c9d12809ef908415c58c6b04da2597a3a1bfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128640"
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