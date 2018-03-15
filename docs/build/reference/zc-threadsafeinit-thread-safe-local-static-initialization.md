---
title: /Zc:threadSafeInit (Thread-sichere lokalen statischen Initialisierung) | Microsoft Docs
ms.custom: 
ms.date: 03/96/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0d44b807a244ea96a982dc2363f90beceb0806b
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc:threadSafeInit (Thread-sichere lokalen statischen Initialisierung)

Die **/Zc:threadSafeInit** (Compileroption) weist den Compiler zum Initialisieren von statischen lokalen (mit Funktionsgültigkeitsbereich) Variablen auf threadsichere Weise entfällt das Erfordernis der manuellen Synchronisierung. Nur die Initialisierung ist threadsicher. Verwenden und Bearbeiten von lokalen statischen Variablen durch mehrere Threads müssen weiterhin manuell synchronisiert werden. Diese Option steht in Visual Studio 2015 ab. Visual Studio wird standardmäßig diese Option aktiviert.

## <a name="syntax"></a>Syntax

**/Zc:threadSafeInit**[`-`]

## <a name="remarks"></a>Hinweise

In standard C ++ 11 muss Block Bereichsvariablen mit statischen oder Thread Speicherdauer 0 (null)-initialisiert werden, bevor andere Initialisierungen stattfindet. Initialisierung tritt auf, wenn das Steuerelement zunächst über die Deklaration der Variablen wird übergeben. Die Deklaration durchläuft das nächste Mal-Steuerelement, wenn während der Initialisierung eine Ausnahme ausgelöst, wird die Variable nicht initialisiert betrachtet und Initialisierung erneut versucht wird wird. Wenn steuerungseingänge die Deklaration gleichzeitig mit der Initialisierung, die gleichzeitige ausführungsblöcke während der Initialisierung abgeschlossen ist. Das Verhalten ist undefiniert, wenn die Deklaration rekursiv während der Initialisierung erneut steuerungseingänge. Visual Studio ab Visual Studio 2015 implementiert standardmäßig dieses Standardverhalten. Dieses Verhalten kann explizit angegeben werden, indem die **/Zc:threadSafeInit** -Compileroption.

Die **/Zc:threadSafeInit** Compileroption ist standardmäßig aktiviert. Die [/ liberalen-](permissive-standards-conformance.md) Option wirkt sich nicht **/Zc:threadSafeInit**.

Threadsichere Initialisierung von statischen lokalen Variablen basiert auf der Code in die universelle C-Laufzeitbibliothek (UCRT) implementiert. Um eine Abhängigkeit zu vermeiden auf die UCRT, oder das Initialisierungsverhalten nicht threadsichere von Versionen von Visual Studio vor Visual Studio 2015 beizubehalten, verwenden die **/Zc:threadSafeInit-** Option. Wenn Sie, dass diese Threadsicherheit nicht erforderlich ist wissen, verwenden Sie diese Option, um etwas kleiner, schneller Code, um statische lokale Deklarationen zu generieren.

Threadsichere statische lokale Variablen mithilfe von lokalen Threadspeicher (TLS) intern um effiziente Ausführung zu ermöglichen, wenn die statische bereits initialisiert wurde. Die Implementierung dieser Funktion basiert auf Windows-Betriebssystem-Unterstützungsfunktionen in Windows Vista und höheren Betriebssystemen. Windows XP, Windows Server 2003 und älteren Betriebssystemen müssen diese Unterstützung keine damit sie nicht die Effizienz nutzen erhalten. Diese Betriebssysteme verfügen auch eine Untergrenze für die Anzahl der TLS-Abschnitte, die geladen werden kann. Überschreiten der TLS kann Abschnitt Grenzwert eines Absturzes zu. Ist dies ein Problem im Code, besonders in Code, die unter älteren Betriebssystemen ausgeführt werden muss, verwenden **/Zc:threadSafeInit-** threadsichere Initialisierungscode zu deaktivieren.

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Aus der **Konfigurationen** Dropdown-Menü, und wählen Sie **alle Konfigurationen**.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:threadSafeInit** oder **/Zc:threadSafeInit-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
