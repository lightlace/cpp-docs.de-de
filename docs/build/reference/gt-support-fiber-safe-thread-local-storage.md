---
title: /GT (Fiber-sicheren lokalen Thread-Speicher unterstützen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 417ac00a446f773a424553e42478a4f0cf58efc6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822515"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (Fiber-sicheren lokalen Thread-Speicher unterstützen)

Unterstützt Fiber-Sicherheit für Daten, die mithilfe statischer lokaler Threadspeicher, d. h. Daten, die mit zugeordneten `__declspec(thread)`.

## <a name="syntax"></a>Syntax

```
/GT
```

## <a name="remarks"></a>Hinweise

Daten, die mit deklariert `__declspec(thread)` durch ein Array von lokalen Threadspeicher (TLS) verwiesen wird. Das TLS-Array ist, ein Array von Adressen, die für die einzelnen Threads vom System verwaltet wird. Jede Adresse in dieses Array gibt den Speicherort der lokalen Thread-Speicher.

Eine Fiber ist ein einfaches Objekt, das besteht aus einem Stapel und einem Registerkontext und kann in verschiedenen Threads geplant werden. Eine Fiber kann auf jedem Thread ausgeführt. Da eine Fiber ausgelagert abrufen kann und höher auf einen anderen Thread neu gestartet, die Adresse des TLS-Arrays muss nicht zwischengespeichert oder optimiert werden als eine allgemeine Teilausdruck auf ein Funktionsaufruf (finden Sie unter den [/Og (globale Optimierungen)](og-global-optimizations.md) option Details). **/ Gt** wird verhindert, dass solche Optimierungen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Optimierung** Eigenschaftenseite.

1. Ändern der **Fiber-sichere Optimierung aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
