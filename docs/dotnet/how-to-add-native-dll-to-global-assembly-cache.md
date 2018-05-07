---
title: 'Vorgehensweise: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7363de172eabc664bcde1e3bf42f8cc499e4251
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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