---
title: /Zc:trigraphs (Trigraphen-Ersetzung)
ms.date: 03/06/2018
f1_keywords:
- /Zc
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 7a20123603030dfe719cd8990018f795df137981
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316001"
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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: trigraphs** oder **/Zc:trigraphs-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
[Trigraphen](../../c-language/trigraphs.md)<br/>
