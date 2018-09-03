---
title: C-Laufzeitfehler R6030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6030
dev_langs:
- C++
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae8eb17fc9d074604586582be08c43289b680b4f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299535"
---
# <a name="c-runtime-error-r6030"></a>C-Laufzeitfehler R6030
CRT nicht initialisiert  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Dieses Problem wird am häufigsten durch bestimmte Softwareprogramme Sicherheit oder in seltenen Fällen durch einen Fehler im Programm verursacht.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Ihre Sicherheitssoftware möglicherweise spezifische Anweisungen zum Umgehen dieses Problems. Überprüfen Sie die Sicherheit Software der Website des Herstellers für Details. Alternativ können prüfen Sie, ob aktualisierte Versionen der Ihre Sicherheitssoftware, oder Wiederholen Sie den anderen Sicherheitssoftware.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler tritt auf, wenn Sie die C-Laufzeit (CRT) verwenden, aber der CRT-Startcode wurde nicht ausgeführt. Es ist möglich, diesen Fehler zu erhalten, wenn der Linker wechseln [/Entry](../../build/reference/entry-entry-point-symbol.md) wird verwendet, um das Überschreiben der standardmäßigen Startadresse, in der Regel **MainCRTStartup**, **WmainCRTStartup** für eine EXE-Datei, Konsole **WinMainCRTStartup** oder **wWinMainCRTStartup** für eine Windows-EXE oder **_DllMainCRTStartup** für eine DLL. Wenn eine der oben genannten Funktionen beim Start aufgerufen wird, wird der C-Laufzeit nicht initialisiert werden. Diese Start-Funktionen werden normalerweise standardmäßig aufgerufen, wenn Sie mit der C-Laufzeitbibliothek verknüpfen und die normalen verwenden **main**, **"wmain"**, **WinMain**, oder  **DllMain** Einstiegspunkte.  
  
 Es ist auch möglich, diese Fehlermeldung erhalten, wenn ein anderes Programm Code Injection Techniken verwendet, um das Abfangen bestimmter Library-DLL aufgerufen. Einige Sicherheitsprogramme setzen verwenden Sie dieses Verfahren. In Versionen von Visual C++ vor Visual Studio 2015 es ist möglich, eine statisch verknüpften CRT-Bibliothek zu verwenden, um das Problem zu beheben, aber dies wird nicht empfohlen, aus Gründen der Sicherheit und Anwendung von Updates. Korrigieren dieses Problem kann durch Endbenutzer Aktion erfordern.