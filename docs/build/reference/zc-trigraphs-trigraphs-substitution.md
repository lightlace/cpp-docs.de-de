---
title: '/ Zc: trigraphs (Trigraphen-Ersetzung) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce8c9d13fa062ddac0f31eac0e20fba1266c7a8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707732"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigraphen-Ersetzung)

Wenn **/Zc: trigraphs** angegeben ist, wird der Compiler ersetzt eine Folge von Zeichen Trigraphen mit der ein entsprechendes Interpunktionszeichen.

## <a name="syntax"></a>Syntax

> **/Zc:trigraphs**[**-**]

## <a name="remarks"></a>Hinweise

Ein *Trigraphen* besteht aus zwei aufeinander folgenden Fragezeichen ("??") gefolgt von einem eindeutigen dritten Zeichen. Die C-Sprachstandard unterstützt Trigraphen für Quelldateien, die einen Zeichensatz zu verwenden, der keine passenden grafische Darstellungen für einige Interpunktionszeichen enthalten. Wenn Trigraphen aktiviert sind, der Compiler ersetzt z.B. den "?? = "Trigraphen mit den Zeichen '#'. C ++ 14 werden die Trigraphen wie in c unterstützt. Standard C ++ 17 entfernt Trigraphen aus der Programmiersprache C++. In C++-Code der **/Zc: trigraphs** Compiler-Option ermöglicht die Ersetzung von trigraphsequenzen durch entsprechendes Interpunktionszeichen. **/Zc:trigraphs-** trigraphenersetzung deaktiviert.

Die **/Zc: trigraphs** Option ist standardmäßig deaktiviert, und die Option ist nicht betroffen, wenn die [/ PERMISSIVE--](permissive-standards-conformance.md) angegeben wird.

Eine Liste der C/C++-Trigraphen und ein Beispiel für die Verwendung von Trigraphen zu verwenden, finden Sie unter [Trigraphen](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: trigraphs** oder **/Zc:trigraphs-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[Trigraphen](../../c-language/trigraphs.md)<br/>
