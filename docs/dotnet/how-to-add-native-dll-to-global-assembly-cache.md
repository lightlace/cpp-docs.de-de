---
title: 'Vorgehensweise: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: b4b886dfef3185c1b3084ed02abcef1ad2630c11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222797"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Vorgehensweise: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache

Sie können eine systemeigene DLL (nicht "COM") im globalen Assemblycache einfügen.

## <a name="example"></a>Beispiel

**/ ASSEMBLYLINKRESOURCE** können Sie eine systemeigene DLL in eine Assembly einzubetten.

Weitere Informationen finden Sie unter [/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
