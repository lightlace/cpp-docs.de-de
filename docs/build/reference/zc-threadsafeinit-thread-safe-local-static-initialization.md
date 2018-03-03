---
title: /Zc:threadSafeInit (Thread-sichere lokalen statischen Initialisierung) | Microsoft Docs
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a03f3ea67c9ecabd6fa68d653a3e1812fb0266cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc:threadSafeInit (Thread-sichere lokalen statischen Initialisierung)  
Die `/Zc:threadSafeInit` (Compileroption) weist den Compiler zum Initialisieren von statischen lokalen (mit Funktionsgültigkeitsbereich) Variablen auf threadsichere Weise entfällt das Erfordernis der manuellen Synchronisierung. Nur die Initialisierung ist threadsicher. Verwenden und Bearbeiten von lokalen statischen Variablen durch mehrere Threads müssen weiterhin manuell synchronisiert werden. Diese Option steht in Visual Studio 2015 ab. Visual Studio wird standardmäßig diese Option aktiviert.  
  
## <a name="syntax"></a>Syntax  
  
`/Zc:threadSafeInit`[`-`]  
  
## <a name="remarks"></a>Hinweise  
  
In standard C ++ 11 muss Block Bereichsvariablen mit statischen oder Thread Speicherdauer 0 (null)-initialisiert werden, bevor andere Initialisierungen stattfindet. Initialisierung tritt auf, wenn das Steuerelement zunächst über die Deklaration der Variablen wird übergeben. Die Deklaration durchläuft das nächste Mal-Steuerelement, wenn während der Initialisierung eine Ausnahme ausgelöst, wird die Variable nicht initialisiert betrachtet und Initialisierung erneut versucht wird wird. Wenn steuerungseingänge die Deklaration gleichzeitig mit der Initialisierung, die gleichzeitige ausführungsblöcke während der Initialisierung abgeschlossen ist. Das Verhalten ist undefiniert, wenn die Deklaration rekursiv während der Initialisierung erneut steuerungseingänge. Visual Studio ab Visual Studio 2015 implementiert standardmäßig dieses Standardverhalten. Dieses Verhalten kann explizit angegeben werden, indem die `/Zc:threadSafeInit` -Compileroption.  
  
Threadsichere Initialisierung von statischen lokalen Variablen basiert auf der Code in die universelle C-Laufzeitbibliothek (UCRT) implementiert. Um eine Abhängigkeit zu vermeiden auf die UCRT, oder das Initialisierungsverhalten nicht threadsichere von Versionen von Visual Studio vor Visual Studio 2015 beizubehalten, verwenden die `/Zc:threadSafeInit-` Option. Wenn Sie, dass diese Threadsicherheit nicht erforderlich ist wissen, verwenden Sie diese Option, um etwas kleiner, schneller Code, um statische lokale Deklarationen zu generieren.  
  
Threadsichere statische lokale Variablen mithilfe von lokalen Threadspeicher (TLS) intern um effiziente Ausführung zu ermöglichen, wenn die statische bereits initialisiert wurde. Die Implementierung dieser Funktion basiert auf Windows-Betriebssystem-Unterstützungsfunktionen in Windows Vista und höheren Betriebssystemen. Windows XP, Windows Server 2003 und älteren Betriebssystemen müssen diese Unterstützung keine damit sie nicht die Effizienz nutzen erhalten. Diese Betriebssysteme verfügen auch eine Untergrenze für die Anzahl der TLS-Abschnitte, die geladen werden kann. Überschreiten der TLS kann Abschnitt Grenzwert eines Absturzes zu. Ist dies ein Problem im Code, besonders in Code, die unter älteren Betriebssystemen ausgeführt werden muss, verwenden `/Zc:threadSafeInit-` threadsichere Initialisierungscode zu deaktivieren.  
  
Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).
2.  Aus der **Konfigurationen** Dropdown-Menü, und wählen Sie **alle Konfigurationen**.
3.  Wählen Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Eigenschaftenseite.
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen `/Zc:threadSafeInit` oder `/Zc:threadSafeInit-` und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch  
[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
[/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)  
