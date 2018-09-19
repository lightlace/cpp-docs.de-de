---
title: -Link (Optionen an Linker übergeben) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /link
dev_langs:
- C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 663407e4948ebc4e3c0a1676c44e8d2b4bd53fcc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704118"
---
# <a name="link-pass-options-to-linker"></a>/link (Optionen an Linker übergeben)

Übergibt ein oder mehrere Optionen des Linkers an den Linker an.

## <a name="syntax"></a>Syntax

```
/link linkeroptions
```

## <a name="arguments"></a>Argumente

*linkeroptions*<br/>
Die Linkeroption oder die Optionen an Linker übergeben werden.

## <a name="remarks"></a>Hinweise

Die **/link** Option und die Optionen des Linkers müssen nach jedem Dateinamen und CL-Optionen angezeigt werden. Ein Leerzeichen ist erforderlich, zwischen **/link** und `linkeroptions`. Weitere Informationen finden Sie unter [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf ein Linker-Eigenschaftenseite.

1. Ändern Sie eine oder mehrere Eigenschaften an.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Diese Compileroption kann nicht programmgesteuert geändert werden.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)