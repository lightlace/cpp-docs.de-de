---
title: /GUARD (Schutzprüfungen aktivieren)
ms.date: 11/04/2016
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
ms.openlocfilehash: e48921e57977cc7a1ca6a580fed78a6a2a960a02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292249"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (Schutzprüfungen aktivieren)

Gibt Unterstützung für die Überprüfung des Ablaufsteuerungsschutzes im ausführbaren Image an.

## <a name="syntax"></a>Syntax

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>Hinweise

Wenn /GUARD:CF angegeben wird, ändert der Linker den Header einer DLL- oder EXE-Datei, um Unterstützung für CFG-Laufzeitüberprüfungen (Control Flow Guard, Ablaufsteuerungsschutz) anzugeben. Der Linker fügt dem Header auch die erforderlichen Ablaufsteuerungs-Zieladressdaten hinzu. Standardmäßig ist /GUARD:CF deaktiviert. Es kann explizit mithilfe von /GUARD:NO deaktiviert werden. Um effektiv zu sein, benötigt/Guard: CF auch die [/DynamicBase (Address Space Layout Randomization verwenden)](dynamicbase-use-address-space-layout-randomization.md) Linkeroption, die standardmäßig aktiviert ist.

Wenn Quellcode kompiliert wird, mithilfe der [/Guard: CF](guard-enable-control-flow-guard.md) auswählen, analysiert der Compiler die ablaufsteuerung durch Untersuchen aller indirekter Aufrufe der möglichen Zieladressen. Der Compiler fügt Code ein, um zu überprüfen, ob sich die Zieladresse einer indirekten Aufrufanweisung zur Laufzeit in der Liste der bekannten Zieladressen befindet. Betriebssysteme, die CFG unterstützen, beenden ein Programm, das bei einer CFG-Laufzeitüberprüfung einen Fehler ausgibt. Dies erschwert es einem Angreifer, schädlichen Code mithilfe von Datenbeschädigung auszuführen, um ein Aufrufziel zu ändern.

Die /GUARD:CF-Option muss dem Compiler und dem Linker angegeben werden, um CFG-fähige ausführbare Images zu erstellen. Code, der kompiliert, aber nicht mit /GUARD:CF verknüpft wurde, verursacht Kosten für Überprüfungen zur Laufzeit, aktiviert aber nicht den CFG-Schutz. Wenn die/Guard: CF-Option angegeben wird, um die `cl` Befehl aus, um die Kompilierung und Verknüpfung in einem Schritt, der Compiler übergibt das Flag an dem Linker. Wenn die **Control Flow Guard** Eigenschaft in Visual Studio festgelegt ist, wird die/Guard: CF-Option dem Compiler und Linker übergeben. Wenn Objektdateien oder Bibliotheken separat kompiliert wurden, die Option explizit angegeben werden der `link` Befehl.

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie **Konfigurationseigenschaften**, **Linker**, **Befehlszeile**.

1. In **zusätzliche Optionen**, geben Sie `/GUARD:CF`.

## <a name="see-also"></a>Siehe auch

[/guard (Ablaufsteuerungsschutz aktivieren)](guard-enable-control-flow-guard.md)<br/>
[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
