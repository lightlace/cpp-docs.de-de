---
title: Kopieren von Quellprojekteigenschaften (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: bc99814e825cda091b6a0b00256ca2d8269ecdd3
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305398"
---
# <a name="copy-sources-project-properties-linux-c"></a>Kopieren von Quellprojekteigenschaften (Linux C++)

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Die auf dieser Eigenschaftenseite festgelegten Eigenschaften gelten für alle Dateien im Projekt, mit Ausnahme derjenigen, deren Eigenschaften auf Dateiebene festgelegt sind.

Eigenschaft | BESCHREIBUNG
--- | ---
Zu kopierende Quellen | Gibt die Quellen an, die auf das Remotesystem kopiert werden sollen. Das Ändern dieser Liste kann die Verzeichnisstruktur, in die Dateien auf dem Remotesystem kopiert werden, verschieben oder anderweitig beeinflussen.
Kopieren der Quellen | Gibt an, ob die Quellen auf das Remotesystem kopiert werden sollen.
Zusätzliche zu kopierende Quellen | Gibt zusätzliche Quellen an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.

@SourcesToCopyRemotely und @DataFilesToCopyRemotely verweisen in der Projektdatei auf Elementgruppen. Bearbeiten Sie die *vcxproj*-Datei wie im folgenden Beispiel, um zu ändern, welche Quellen oder Datendateien remote kopiert werden.

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
