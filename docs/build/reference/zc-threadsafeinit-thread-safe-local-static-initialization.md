---
title: '/ Zc: threadsafeinit (threadsichere lokale statische Initialisierung)'
ms.date: 03/14/2018
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
ms.openlocfilehash: a0a5edda3d0d178a03fa98cf689b257cd5ab3f53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605828"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/ Zc: threadsafeinit (threadsichere lokale statische Initialisierung)

Die **/Zc: threadsafeinit** -Compileroption informiert den Compiler an, Initialisieren von statischen lokalen (mit Funktionsgültigkeitsbereich) Variablen auf threadsichere Weise beseitigt die Notwendigkeit der manuellen Synchronisierung. Nur die Initialisierung ist threadsicher. Verwenden und Ändern von lokalen statischen Variablen durch mehrere Threads müssen weiterhin manuell synchronisiert werden. Diese Option ist ab Visual Studio 2015 verfügbar. Standardmäßig werden in Visual Studio diese Option aktiviert.

## <a name="syntax"></a>Syntax

> **/Zc:threadSafeInit**[**-**]

## <a name="remarks"></a>Hinweise

Im C ++ 11-standard muss Block Variablen im Bereich mit statischen oder threadspeicherdauer 0 (null)-initialisiert werden, bevor andere Initialisierungen stattfindet. Initialisierung tritt auf, wenn die Steuerung zunächst über die Deklaration der Variablen übergeben. Die Deklaration durchläuft das nächste Mal-Steuerelement, wenn während der Initialisierung wird eine Ausnahme ausgelöst, wird die Variable nicht initialisiert betrachtet und Initialisierung erneut versucht wird wird. Wenn das Steuerelement geht in der Deklaration gleichzeitig mit der Initialisierung, die gleichzeitige Ausführung blockiert, während der Initialisierung abgeschlossen ist. Das Verhalten ist nicht definiert, wenn das Steuerelement die Deklaration rekursiv während der Initialisierung erneut eingegeben werden. Visual Studio ab Visual Studio 2015 implementiert standardmäßig dieses Standardverhalten. Dieses Verhalten kann explizit angegeben werden, indem die **/Zc: threadsafeinit** -Compileroption.

Die **/Zc: threadsafeinit** Compiler-Option ist standardmäßig aktiviert. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option hat keine Auswirkungen auf **/Zc: threadsafeinit**.

Threadsichere Initialisierung von lokalen statischen Variablen basiert auf in die universelle C-Laufzeitbibliothek (UCRT) implementiert. Um zu vermeiden, die UCRT eine Abhängigkeit übernehmen oder das Initialisierungsverhalten nicht threadsicheren von Versionen von Visual Studio vor Visual Studio 2015 beizubehalten, verwenden die **/Zc:threadSafeInit-** Option. Wenn Sie, dass diese Threadsicherheit nicht erforderlich ist wissen, verwenden Sie diese Option, um etwas kleiner, schneller Code rund um die statische lokale Deklarationen zu generieren.

Threadsichere statische lokale Variablen verwenden lokalen Threadspeicher (TLS) intern, um die effiziente Ausführung zu ermöglichen, wenn die statische bereits initialisiert wurde. Die Implementierung dieser Funktion basiert auf Windows-Betriebssystem-Support-Funktionen in Windows Vista und späteren Betriebssystemen. Windows XP, Windows Server 2003 und ältere Betriebssysteme dieser Unterstützung keine, sodass sie nicht den Vorteil der Effizienz erzielen. Diese Betriebssysteme verfügen auch eine Untergrenze für die Anzahl der TLS-Abschnitte, die geladen werden kann. Überschreiten die TLS kann Abschnitt Grenzwert einen Absturz verursachen. Ist dies ein Problem in Ihrem Code, insbesondere in Code, die unter älteren Betriebssystemen ausgeführt werden muss verwenden **/Zc:threadSafeInit-** den threadsichere Initialisierungscode zu deaktivieren.

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Von der **Konfigurationen** Dropdownmenü, und wählen Sie **alle Konfigurationen**.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: threadsafeinit** oder **/Zc:threadSafeInit-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
