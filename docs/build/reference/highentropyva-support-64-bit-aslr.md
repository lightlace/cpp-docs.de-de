---
title: / HIGHENTROPYVA (Unterstützung für 64-Bit-ASLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66fe8f20631d576264eab836f822a414c1244d5b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223429"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (Unterstützung für 64-Bit ASLR)

Gibt an, ob das ausführbare Image 64-bit-ASLR mit hoher Entropie unterstützt.

## <a name="syntax"></a>Syntax

> **/ HIGHENTROPYVA**[**: NO**]

## <a name="remarks"></a>Hinweise

**/ HIGHENTROPYVA** ändert den Header einer *ausführbares Image*, eine DLL-Datei oder der .exe-Datei, um anzugeben, ob ASLR den gesamten 64-Bit-Adressraum verwenden kann. Wenn diese Option auf einer ausführbaren Datei und allen Modulen festgelegt wird, von denen sie abhängt, kann ein 64-Bit-ASLR unterstützendes Betriebssystem für die Segmente des ausführbaren Images zur Ladezeit ein Rebase ausführen, indem zufällige Adressen in einem virtuellen 64-Bit-Adressbereich verwendet werden. Aufgrund dieses großen Adressbereichs ist es für einen Angreifer schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.

In der Standardeinstellung **/highentropyva** für ausführbare 64-Bit-Images aktiviert ist. Diese Option erfordert [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md), die auch für 64-Bit-Images standardmäßig aktiviert ist. **/ HIGHENTROPYVA** gilt nicht für ausführbare 32-Bit-Images, in denen der Linker die Option ignoriert. Um diese Option explizit zu deaktivieren, verwenden **/HIGHENTROPYVA:NO**.

Für **/highentropyva** wirksam zur Ladezeit [/DynamicBase](dynamicbase-use-address-space-layout-randomization.md) muss ebenfalls aktiviert werden. **/ DYNAMICBASE** ist standardmäßig aktiviert und ist erforderlich, um ASLR in Windows Vista und späteren Betriebssystemen zu ermöglichen. Frühere Versionen von Windows ignorieren dieses Flag an.

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. In **zusätzliche Optionen**, geben Sie `/HIGHENTROPYVA` oder `/HIGHENTROPYVA:NO`.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Windows ISV-Softwaresicherheitsmaßnahmen](https://msdn.microsoft.com/library/bb430720.aspx)
