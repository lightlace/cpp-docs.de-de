---
title: UWP-Apps, Windows-Runtime und die C-Laufzeit
ms.date: 02/02/2019
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
ms.openlocfilehash: ae57390dc916116b8d799b9f937ff882abaef970
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763888"
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>UWP-Apps, Windows-Runtime und die C-Laufzeit

UWP-Apps (Universelle Windows-Plattform) sind in Windows-Runtime ausgeführte Programme, die unter Windows 8 ausgeführt werden. Bei der Windows-Runtime handelt es sich um eine vertrauenswürdige Umgebung, die die Funktionen, Variablen und Ressourcen steuert, die für eine UWP-App verfügbar sind. Standardmäßig verhindern Windows-Runtime-Einschränkungen jedoch die Verwendung der meisten Funktionen der C-Laufzeitbibliothek (CRT) in UWP-Apps.

Die folgenden CRT-Funktionen werden durch die Windows-Runtime nicht unterstützt:

- Die meisten CRT-Funktionen, die mit nicht unterstützten Funktionen in Zusammenhang stehen.

   Beispielsweise kann eine UWP-App mithilfe der **exec**- und **spawn**-Serie von Routinen keinen Prozess erstellen.

   Wenn eine CRT-Funktion in einer UWP-App nicht unterstützt wird, ist dies im zugehörigen Referenzartikel vermerkt.

- Die meisten Zeichen- und Mehrbytefunktionen.

   Allerdings werden Unicode und ANSI-Text unterstützt.

- Umgebungsvariablen.

- Das Konzept eines aktuellen Arbeitsverzeichnisses.

- UWP-Apps und DLL-Dateien, die mit der CRT statisch verknüpft sind und mithilfe der Compileroptionen [/MT](../build/reference/md-mt-ld-use-run-time-library.md) oder `/MTd` erstellt werden.

   Also eine App, die eine statische Multithread-Version der CRT verwendet.

- Eine mithilfe der Compileroption [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) erstellte App.

   Also eine Debug-, Multithread- und DLL-spezifische Version der CRT. Eine solche Anwendung wird in Windows-Runtime nicht unterstützt.

Eine vollständige Liste der CRT-Funktionen, die in einer UWP-App nicht verfügbar sind, und Vorschläge für alternative Funktionen finden Sie unter [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>Siehe auch

[Kompatibilität](../c-runtime-library/compatibility.md)<br/>
[CRT-Funktionen, die nicht von Windows-Runtime unterstützt werden](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Erstellen einer Konsolen-App für die Universelle Windows-Plattform](/windows/uwp/launch-resume/console-uwp)
