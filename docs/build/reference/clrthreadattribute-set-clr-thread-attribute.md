---
title: /CLRTHREADATTRIBUTE (Festlegen des CLR-Threadattributs)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: 3aae02a004226bf1042488d3a654dae9f751e8af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668480"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (Festlegen des CLR-Threadattributs)

Geben Sie explizit das Threadingattribut für den Einstiegspunkt des CLR-Programms.

## <a name="syntax"></a>Syntax

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>Parameter

**DER MTA**<br/>
Wendet das MTAThreadAttribute-Attribut auf den Einstiegspunkt des Programms an.

**KEINE**<br/>
Identisch mit/CLRTHREADATTRIBUTE nicht angegeben.  Können die Common Language Runtime (CLR) die Standardeinstellung Threadingattribut festgelegt.

**STA**<br/>
Wendet das STAThreadAttribute-Attribut auf den Einstiegspunkt des Programms an.

## <a name="remarks"></a>Hinweise

Festlegen der Thread-Attribut ist nur gültig beim Erstellen einer .exe, wie sie den Einstiegspunkt des Hauptthreads wirkt sich auf.

Wenn Sie der Standardeinstiegspunkt ("Main" oder "Wmain, z. B.") Geben Sie dem Threadingmodell entweder mithilfe von/CLRTHREADATTRIBUTE oder platziert das threading-Attribut ("STAThreadAttribute" oder "MTAThreadAttribute") für die Standard-Eintrag-Funktion.

Wenn Sie einen nicht standardmäßigen Einstiegspunkt verwenden, geben Sie das Threadingmodell entweder mithilfe von/CLRTHREADATTRIBUTE oder durch Platzieren des-Attribut für die Funktion nicht dem Standard-Eintrag, und geben Sie den nicht standardmäßigen Einstiegspunkt mit [/Entry](../../build/reference/entry-entry-point-symbol.md) .

Wenn Sie das Threadingmodell angegeben wird, im Quellcode nicht mit dem Threadingmodell mit/CLRTHREADATTRIBUTE angegebene übereinstimmt, der Linker/CLRTHREADATTRIBUTE ignoriert und wenden das Threadingmodell im Quellcode angegeben.

Es wird für Sie mit Single-threading, z. B. erforderlich sein, wenn CLR-Programms über ein COM-Objekt hostet, die Single-threading verwendet.  Wenn das CLR-Programm, kann nicht es ein COM-Objekt hosten, die Single-threading verwendet.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **CLR-Threadattributs** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)