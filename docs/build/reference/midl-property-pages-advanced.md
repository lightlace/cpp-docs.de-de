---
title: 'MIDL-Eigenschaftenseiten: Erweitert'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
ms.openlocfilehash: 350563d140823910667812930f9283c7640cc1ff
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825490"
---
# <a name="midl-property-pages-advanced"></a>MIDL-Eigenschaftenseiten: Erweitert

Die Eigenschaftenseite **Erweitert** im Ordner **MIDL** gibt die folgenden MIDL-Compileroptionen an:

- Aktivieren der Fehlerüberprüfung ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Überprüfen der Speicherbelegungen ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Überprüfen der Begrenzungen ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Überprüfen des Enumerationsbereichs ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Überprüfen der Verweiszeiger ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Überprüfen der Stub-Daten ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- Überprüfen von Parametern ([/robust](https://msdn.microsoft.com/library/windows/desktop/aa367363)) \*

- Ausrichten der Strukturmembers ([/Zp](https://msdn.microsoft.com/library/windows/desktop/aa367388))

- Umleiten der Ausgabe ([/o](https://msdn.microsoft.com/library/windows/desktop/aa367351))

- C-Präprozessoroptionen ([/cpp_opt](https://msdn.microsoft.com/library/windows/desktop/aa367318))

- Aufheben der Präprozessordefinitionen ([/U](https://msdn.microsoft.com/library/windows/desktop/aa367373))

\*/robust wird nur bei der Erstellung für einen Computer mit Windows 2000 oder höher verwendet. Wenn Sie ein ATL-Projekt erstellen und /robust verwenden möchten, müssen Sie die folgende Zeile in der Datei „dlldatax.c“ ändern:

```
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM
to
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM
```

Informationen zum Zugreifen auf die **erweitert** Eigenschaftenseite in der **MIDL** Ordner finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

Informationen über den programmgesteuerten Zugriff auf die MIDL-Optionen für C++-Projekte finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten "MIDL"](midl-property-pages.md)
