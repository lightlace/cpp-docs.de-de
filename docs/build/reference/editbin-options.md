---
title: EDITBIN-Optionen | Microsoft Docs
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
ms.openlocfilehash: 1922e410b0151337ce403e24d20ae90b7e964cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="editbin-options"></a>EDITBIN-Optionen
EDITBIN können um Objektdateien, ausführbaren Dateien und Dynamic Link Libraries (DLLs) zu ändern. Optionen zum Angeben der Änderungen, die EDITBIN vornimmt.  
  
 Eine Option besteht aus einem Optionsbezeichner, entweder einem Bindestrich (-) oder einem Schrägstrich (/), gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben Argumente, die nach einem Doppelpunkt (:)) angegeben werden. Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Optionsnamen und ihren Schlüsselwort Argumente oder die Datei bestehenden Argumenten wird die Groß-/Kleinschreibung nicht berücksichtigt. Z. B. - Bindung und/BIND dieselbe Bedeutung.  
  
 EDITBIN enthält die folgenden Optionen:  
  
|Option|Zweck|  
|------------|-------------|  
|[/ALLOWBIND](../../build/reference/allowbind.md)|Gibt an, ob eine DLL gebunden werden kann.|  
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|Gibt an, DLL oder ausführbare Datei Manifestsuche Verhalten.|  
|[/APPCONTAINER](../../build/reference/appcontainer.md)|Gibt an, ob die app in einer AppContainer ausgeführt werden muss, z. B. einer uwp-app.|  
|[/BIND](../../build/reference/bind.md)|Legt die Adressen für die Einstiegspunkte in die angegebenen Objekte zur Ladezeit Geschwindigkeit fest.|  
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|Gibt an, ob die DLL oder ausführbaren Images nach dem Zufallsprinzip zur Ladezeit ein REBASE werden kann Adresse Space Layout Randomization (ASLR).|  
|[/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Interner Fehler an Microsoft gemeldet.|  
|[/HEAP](../../build/reference/heap.md)|Legt die Größe des ausführbaren Images Heap in Bytes fest.|  
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Gibt an, ob die DLL oder ausführbaren Images mit hoher Entropie (64-Bit) Adresse Space Layout Randomization (ASLR) unterstützt.|  
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Gibt an, ob die digitale Signatur zur Ladezeit überprüft werden soll.|  
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Gibt an, ob das Objekt Adressen unterstützt, die größer als 2 GB sind.|  
|[/ NOLOGO](../../build/reference/nologo-editbin.md)|Unterdrückt den Startbanner EDITBIN an.|  
|[/NXCOMPAT](../../build/reference/nxcompat.md)|Gibt an, ob das ausführbare Image mit Datenausführungsverhinderung kompatibel ist.|  
|[/REBASE](../../build/reference/rebase.md)|Legt die Basisadressen für die angegebenen Objekte.|  
|[/RELEASE](../../build/reference/release.md)|Legt die Prüfsumme im Header fest.|  
|[/ SECTION](../../build/reference/section-editbin.md)|Überschreibt die Attribute eines Abschnitts.|  
|[/STACK](../../build/reference/stack.md)|Legt das ausführbare Image Stapelgröße in Bytes fest.|  
|[/SUBSYSTEM](../../build/reference/subsystem.md)|Gibt die ausführungsumgebung bereitstellt.|  
|[/SWAPRUN](../../build/reference/swaprun.md)|Gibt an, dass das ausführbare Image muss in die Auslagerungsdatei kopiert, und führen Sie von dort aus.|  
|[/TSAWARE](../../build/reference/tsaware.md)|Gibt an, dass die app in einer Umgebung mit mehreren Benutzern ausgeführt werden sollen.|  
|[/VERSION](../../build/reference/version.md)|Legt die Versionsnummer im Header fest.|  
  
## <a name="see-also"></a>Siehe auch  
 [C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)   
 [EDITBIN-Referenz](../../build/reference/editbin-reference.md)