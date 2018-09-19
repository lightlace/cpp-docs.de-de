---
title: EDITBIN-Optionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0850f242b8368a9592a5622e627c781b4df4cde5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710137"
---
# <a name="editbin-options"></a>EDITBIN-Optionen

EDITBIN können Sie die um Objektdateien, ausführbaren Dateien und Dynamic Link Libraries (DLLs) zu ändern. Optionen angeben, die Änderungen, die EDITBIN macht.

Eine Option besteht aus einem Optionsbezeichner, entweder einen Bindestrich (-) oder einem Schrägstrich (/), gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben Argumente, die nach einem Doppelpunkt (:) angegeben werden. Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Optionsnamen und ihren Schlüsselwort Argumente oder Argumente für Namen werden nicht beachtet. Z. B. - Bindung und/BIND dieselbe Bedeutung.

EDITBIN enthält die folgenden Optionen:

|Option|Zweck|
|------------|-------------|
|[/ALLOWBIND](../../build/reference/allowbind.md)|Gibt an, ob eine DLL gebunden werden kann.|
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|Gibt an, DLL oder ausführbare Datei Manifestsuche Verhalten.|
|[/APPCONTAINER](../../build/reference/appcontainer.md)|Gibt an, ob die app in einer AppContainer ausgeführt werden muss, z. B. eine UWP-app.|
|[/BIND](../../build/reference/bind.md)|Legt die Adressen für die Einstiegspunkte in die angegebenen Objekte zur Ladezeit Geschwindigkeit fest.|
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|Gibt an, ob die DLL oder ausführbaren Images nach dem Zufallsprinzip zur Ladezeit ein REBASE ausgeführt werden kann mit der Adresse Space Layout Randomization (ASLR).|
|[/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Berichte von internen Fehlern an Microsoft.|
|[/HEAP](../../build/reference/heap.md)|Legt die Größe des Heaps für das ausführbare Image in Bytes fest.|
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Gibt an, ob die DLL oder ausführbaren Images mit hoher Entropie (64-Bit) Adresse Space Layout Randomization (ASLR) unterstützt.|
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Gibt an, ob die digitale Signatur beim Laden der überprüft werden soll.|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Gibt an, ob das Objekt Adressen unterstützt, die größer als 2 GB sind.|
|[/ NOLOGO](../../build/reference/nologo-editbin.md)|Unterdrückt den Startbanner EDITBIN an.|
|[/NXCOMPAT](../../build/reference/nxcompat.md)|Gibt an, ob das ausführbare Image mit Windows-Datenausführungsverhinderung kompatibel ist.|
|[/REBASE](../../build/reference/rebase.md)|Legt fest, die Basisadressen für den angegebenen Objekten.|
|[/RELEASE](../../build/reference/release.md)|Legt die Prüfsumme im Header fest.|
|[/ SECTION](../../build/reference/section-editbin.md)|Überschreibt die Attribute eines Abschnitts.|
|[/STACK](../../build/reference/stack.md)|Legt das ausführbare Image Stapelgröße in Bytes fest.|
|[/SUBSYSTEM](../../build/reference/subsystem.md)|Gibt an, der die ausführungsumgebung.|
|[/SWAPRUN](../../build/reference/swaprun.md)|Gibt an, dass das ausführbare Image in die Auslagerungsdatei kopiert, und klicken Sie dann von dort aus ausgeführt werden muss.|
|[/TSAWARE](../../build/reference/tsaware.md)|Gibt an, dass die app in einer Umgebung mit mehreren Benutzern ausgeführt werden sollen.|
|[/VERSION](../../build/reference/version.md)|Legt die Versionsnummer im Header fest.|

## <a name="see-also"></a>Siehe auch

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)<br/>
[EDITBIN-Referenz](../../build/reference/editbin-reference.md)