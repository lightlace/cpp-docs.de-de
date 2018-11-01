---
title: 'Gewusst wie: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 1b11ebfae704ca1529113a00b463df728c85fe60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641362"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Gewusst wie: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache

Sie können eine systemeigene DLL (nicht "COM") im globalen Assemblycache einfügen.

## <a name="example"></a>Beispiel

**/ ASSEMBLYLINKRESOURCE** können Sie eine systemeigene DLL in eine Assembly einzubetten.

Weitere Informationen finden Sie unter [/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)