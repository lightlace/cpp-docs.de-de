---
title: /DYNAMICBASE (Address Space Layout Randomization verwenden)
ms.date: 06/12/2018
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
ms.openlocfilehash: a3495de3ec72bcac78cdee2f5f3265864e7a2932
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807753"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (Address Space Layout Randomization verwenden)

Gibt an, ob ein ausführbares Image generiert werden, das nach dem Zufallsprinzip ein REBASE können zur Ladezeit ausgeführt werden mit der Address Space Layout Randomization (ASLR)-Funktion von Windows, die zuerst in Windows Vista verfügbar war.

## <a name="syntax"></a>Syntax

> **/DYNAMICBASE**[**:NO**]

## <a name="remarks"></a>Hinweise

Die **/DynamicBase** Option ändert den Header einer *ausführbares Image*, eine .dll oder .exe-Datei, um anzugeben, ob die Anwendung nach dem Zufallsprinzip ein zur Ladezeit REBASE sollte und ermöglicht es virtuelle Adresse Zuordnung Randomization, das wirkt sich die virtuellen Speicheradresse des Heaps, stapeln und anderen Betriebssystem-Zuordnungen. Die **/DynamicBase** Option gilt für 32-Bit- und 64-Bit-Images. ASLR wird unter Windows Vista und späteren Betriebssystemen unterstützt. Die Option wird von älteren Betriebssystemen ignoriert.

In der Standardeinstellung **/DynamicBase** aktiviert ist. Verwenden Sie zum Deaktivieren dieser Option **/DYNAMICBASE:NO**. Die **/DynamicBase** Option ist erforderlich, damit die [/highentropyva](highentropyva-support-64-bit-aslr.md) Option aus, um die Auswirkungen haben.

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **erweitert** Eigenschaftenseite.

1. Ändern der **Zufällige Basisadresse** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linker-Referenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [Windows ISV-Softwaresicherheitsmaßnahmen](https://msdn.microsoft.com/library/bb430720.aspx)