---
title: EDITBIN-Optionen
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
ms.openlocfilehash: e7338c6a45d74aa8efac1b72683cca7661c62e0a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820103"
---
# <a name="editbin-options"></a>EDITBIN-Optionen

EDITBIN können Sie die um Objektdateien, ausführbaren Dateien und Dynamic Link Libraries (DLLs) zu ändern. Optionen angeben, die Änderungen, die EDITBIN macht.

Eine Option besteht aus einem Optionsbezeichner, entweder einen Bindestrich (-) oder einem Schrägstrich (/), gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben Argumente, die nach einem Doppelpunkt (:) angegeben werden. Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Optionsnamen und ihren Schlüsselwort Argumente oder Argumente für Namen werden nicht beachtet. Z. B. - Bindung und/BIND dieselbe Bedeutung.

EDITBIN enthält die folgenden Optionen:

|Option|Zweck|
|------------|-------------|
|[/ALLOWBIND](allowbind.md)|Gibt an, ob eine DLL gebunden werden kann.|
|[/ALLOWISOLATION](allowisolation.md)|Gibt an, DLL oder ausführbare Datei Manifestsuche Verhalten.|
|[/APPCONTAINER](appcontainer.md)|Gibt an, ob die app in einer AppContainer ausgeführt werden muss, z. B. eine UWP-app.|
|[/BIND](bind.md)|Legt die Adressen für die Einstiegspunkte in die angegebenen Objekte zur Ladezeit Geschwindigkeit fest.|
|[/DYNAMICBASE](dynamicbase.md)|Gibt an, ob die DLL oder ausführbaren Images nach dem Zufallsprinzip zur Ladezeit ein REBASE ausgeführt werden kann mit der Adresse Space Layout Randomization (ASLR).|
|[/ERRORREPORT](errorreport-editbin-exe.md)|Berichte von internen Fehlern an Microsoft.|
|[/HEAP](heap.md)|Legt die Größe des Heaps für das ausführbare Image in Bytes fest.|
|[/HIGHENTROPYVA](highentropyva.md)|Gibt an, ob die DLL oder ausführbaren Images mit hoher Entropie (64-Bit) Adresse Space Layout Randomization (ASLR) unterstützt.|
|[/INTEGRITYCHECK](integritycheck.md)|Gibt an, ob die digitale Signatur beim Laden der überprüft werden soll.|
|[/LARGEADDRESSAWARE](largeaddressaware.md)|Gibt an, ob das Objekt Adressen unterstützt, die größer als 2 GB sind.|
|[/NOLOGO](nologo-editbin.md)|Unterdrückt den Startbanner EDITBIN an.|
|[/NXCOMPAT](nxcompat.md)|Gibt an, ob das ausführbare Image mit Windows-Datenausführungsverhinderung kompatibel ist.|
|[/REBASE](rebase.md)|Legt fest, die Basisadressen für den angegebenen Objekten.|
|[/RELEASE](release.md)|Legt die Prüfsumme im Header fest.|
|[/SECTION](section-editbin.md)|Überschreibt die Attribute eines Abschnitts.|
|[/STACK](stack.md)|Legt das ausführbare Image Stapelgröße in Bytes fest.|
|[/SUBSYSTEM](subsystem.md)|Gibt an, der die ausführungsumgebung.|
|[/SWAPRUN](swaprun.md)|Gibt an, dass das ausführbare Image in die Auslagerungsdatei kopiert, und klicken Sie dann von dort aus ausgeführt werden muss.|
|[/TSAWARE](tsaware.md)|Gibt an, dass die app in einer Umgebung mit mehreren Benutzern ausgeführt werden sollen.|
|[/VERSION](version.md)|Legt die Versionsnummer im Header fest.|

## <a name="see-also"></a>Siehe auch

[Zusätzliche MSVC-Buildtools](c-cpp-build-tools.md)<br/>
[EDITBIN-Referenz](editbin-reference.md)
