---
title: C-Laufzeitfehler R6030
ms.date: 11/04/2016
f1_keywords:
- R6030
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
ms.openlocfilehash: 7f5c61d9b39b1d655bcbf3d42ea870370ddf2842
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400018"
---
# <a name="c-runtime-error-r6030"></a>C-Laufzeitfehler R6030

CRT, die nicht initialisiert

> [!NOTE]
> Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Dieses Problem wird meist durch bestimmte Softwareprogramme Sicherheit oder nur selten, durch einen Fehler im Programm verursacht.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Ihre Sicherheitssoftware möglicherweise spezifische Anweisungen für dieses Problem zu entschärfen. Überprüfen Sie die Security Software der Website des Herstellers für Details. Klicken Sie alternativ prüfen, ob aktualisierte Versionen Ihrer Sicherheitssoftware, oder versuchen Sie es anderen Sicherheitssoftware.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler tritt auf, wenn Sie die C-Laufzeit (CRT) verwenden, aber die CRT-Startcode wurde nicht ausgeführt. Es ist möglich, diese Fehlermeldung, wenn der Linkerschalter [/Entry](../../build/reference/entry-entry-point-symbol.md) dient zum Überschreiben der standardmäßigen Start-Adresse in der Regel **MainCRTStartup**, **WmainCRTStartup** für eine EXE-Datei, Konsole **WinMainCRTStartup** oder **wWinMainCRTStartup** für eine Windows-EXE-Datei ein, oder **_DllMainCRTStartup** für eine DLL. Wenn eine der oben genannten Funktionen beim Start aufgerufen wird, wird der C-Laufzeit nicht initialisiert werden. Diese Start-Funktionen werden normalerweise standardmäßig aufgerufen, wenn Sie mit der C-Laufzeitbibliothek verknüpfen, und verwenden Sie den gewohnten **main**, **Wmain**, **WinMain**, oder  **DllMain** Einstiegspunkte.

Es ist auch möglich, diese Fehlermeldung, wenn ein anderes Programm Code Injection-Technologien verwendet, um bestimmte DLL-Bibliotheksaufrufe abfangen. Einige Sicherheitsprogramme tiefgreifende verwenden Sie dieses Verfahren. In Versionen von Visual C++ vor Visual Studio 2015 es ist möglich, eine statisch verknüpften CRT-Bibliothek zu verwenden, um das Problem zu beheben, aber dies wird nicht empfohlen aus Gründen der Sicherheit und Updates. Beheben dieses Problem unter Umständen Aktion des Endbenutzers.