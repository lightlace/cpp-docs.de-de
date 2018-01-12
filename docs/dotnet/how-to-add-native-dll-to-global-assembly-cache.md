---
title: "Vorgehensweise: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: be55fd47cd6024d0660ed0c3e4594c9430f80cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Gewusst wie: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache
Sie können eine systemeigene DLL (nicht COM) im globalen Assemblycache ablegen.  
  
## <a name="example"></a>Beispiel  
 **/ ASSEMBLYLINKRESOURCE** können Sie eine systemeigene DLL in eine Assembly einzubetten.  
  
 Weitere Informationen finden Sie unter [/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)