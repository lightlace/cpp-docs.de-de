---
title: Gegenseitige Importe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- mutual DLL imports [C++]
- AFX_DATA
- importing DLLs [C++], mutual imports
- mutually importing executable files [C++]
- AFX_EXT_CLASS macro
- circular imports
- _AFXEXT preprocessor symbol
- DLLs [C++], importing
- executable files [C++], importing
- extension DLLs [C++], mutual imports
- exporting DLLs [C++], mutual imports
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7aee01e72fb8386b6aee7e6a505424b4138f45d7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704841"
---
# <a name="mutual-imports"></a>Gegenseitige Importe

Exportieren oder Importieren in eine andere ausführbare Datei enthält Komplikationen, wenn die Importe gegenseitig (oder zirkuläre) sind. Zwei DLLs werden z. B. Symbole wie wechselseitig rekursive Funktionen voneinander importieren.

Das Problem mit der gegenseitig importierende ausführbare Dateien (normalerweise DLLs) ist, dass keine erstellt werden kann, ohne zuerst die andere erstellt. Jeder Buildprozess erfordert, als Eingabe eine Importbibliothek, die von den anderen Buildprozess erstellt.

Die Lösung ist, das LIB-Dienstprogramm mit der Option/DEF zu verwenden, die eine Importbibliothek erstellt wird, ohne die ausführbare Datei zu erstellen. Mithilfe dieses Hilfsprogramms können Sie erstellen, alle Importbibliotheken, die Sie benötigen, unabhängig davon, wie viele DLLs beteiligt sind, oder wie kompliziert die Abhängigkeiten sind.

Die allgemeine Lösung für die Behandlung von gegenseitiger Imports ist:

1. Nehmen Sie wiederum jede DLL-Datei. (Beliebiger Reihenfolge ist möglich, obwohl einige Aufträge besser geeignet sind.) Wenn alle erforderlichen Importbibliotheken vorhanden und aktuell sind, führen die Verknüpfung, um die ausführbare Datei (DLL) zu erstellen. Dies führt zu eine Importbibliothek. Führen Sie andernfalls LIB, um eine Importbibliothek zu erzeugen.

   Ausführen von LIB mit der/DEF-Option erstellt eine zusätzliche Datei mit ein. EXP-Erweiterung. Die. EXP-Datei muss später verwendet werden, um die ausführbare Datei zu erstellen.

1. Nach der Verwendung von entweder "LINK" oder "LIB aller Importbibliotheken erstellen, wechseln Sie zurück, und führen Sie die Verknüpfung, um alle ausführbaren Dateien zu erstellen, die nicht im vorherigen Schritt erstellt wurden. Beachten Sie, dass die entsprechende EXP-Datei muss in der Linkzeile angegeben werden.

   Wenn Sie das Dienstprogramm "LIB" weiter oben, um eine Importbibliothek für DLL1 zu erzeugen ausführen musste, würde LIB sowie für die Datei DLL1.exp erstellt haben. Sie müssen die DLL1.exp als Eingabe für den LINK verwenden, wenn DLL1.dll erstellen.

Die folgende Abbildung zeigt eine Lösung für zwei sich gegenseitig importierende DLLs, DLL1 und DLL2. Schritt 1 ist die/DEF-Option festgelegt ist, auf DLL1 LIB ausgeführt. Schritt 1 erzeugt DLL1.lib, einer Importbibliothek und DLL1.exp. In Schritt 2 wird die Importbibliothek verwendet, um DLL2 zu erstellen, die wiederum eine Importbibliothek für die DLL2 erzeugt. Schritt 3 erstellt DLL1, mithilfe der DLL1.exp und DLL2.lib als Eingabe an. Beachten Sie, dass eine .exp-Datei für DLL2 nicht erforderlich ist, da LIB nicht zum Erstellen DLL2s Importbibliothek verwendet wurde.

![Mithilfe von gegenseitigen Importen zum Verknüpfen von zwei DLLs](../build/media/vc37yj1.gif "mithilfe von gegenseitigen Importen zum Verknüpfen von zwei DLLs")<br/>
Verknüpfen von zwei DLLs mit gegenseitigen Importen

## <a name="limitations-of-afxext"></a>Einschränkungen von _AFXEXT

Sie können die `_AFXEXT` Präprozessorsymbol für die MFC-Erweiterungs-DLLs, solange Sie nicht über mehrere Ebenen von MFC-Erweiterungs-DLLs verfügen. Wenn Sie MFC-Erweiterungs-DLLs, die aufrufen oder das Ableiten von Klassen in Ihren eigenen MFC-Erweiterungs-DLLs, die dann von den MFC-Klassen abgeleitet werden verfügen, müssen Sie eigene Präprozessorsymbol verwenden, um Mehrdeutigkeiten zu vermeiden.

Das Problem besteht darin, in Win32, müssen Sie explizit deklarieren, alle Daten als **__declspec(dllexport)** ist dies über eine DLL exportiert werden und **von "__declspec(dllimport)" "** ist dies aus einer DLL importiert werden. Beim Definieren von `_AFXEXT`, die MFC-Header verwenden, stellen sicher, dass **AFX_EXT_CLASS** ordnungsgemäß definiert ist.

Wenn Sie verfügen über mehrere Ebenen, ein Symbol z. B. **AFX_EXT_CLASS** ist nicht ausreichend, da eine MFC-Erweiterungs-DLL kann werden Exportieren von neuen Klassen als auch andere Klassen aus einer anderen MFC-Erweiterungs-DLL importieren. Um dieses Problem zu beheben, verwenden Sie ein spezielles Präprozessorsymbol, das angibt, dass Sie die DLL selbst im Vergleich zur Verwendung der DLL erstellen. Beispiel: Angenommen Sie, zwei MFC-Erweiterungs-DLLs, eine DLL- und B.dll. Jeder exportieren bzw. einige Klassen in A.h bzw. B.h. B.dll verwendet die Klassen von A.dll. Die Headerdateien würde etwa wie folgt aussehen:

```
/* A.H */
#ifdef A_IMPL
   #define CLASS_DECL_A   __declspec(dllexport)
#else
   #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ ... class definition ... };

// B.H
#ifdef B_IMPL
   #define CLASS_DECL_B   __declspec(dllexport)
#else
   #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ ... class definition ... };
...
```

Wenn A.dll erstellt wird, wird er erstellt, mit `/D A_IMPL` und wenn B.dll erstellt wird, wird er erstellt, mit `/D B_IMPL`. Durch die Verwendung separater Symbole für jede DLL-Datei, `CExampleB` wird exportiert und `CExampleA` wird beim Erstellen von B.dll importiert. `CExampleA` wird beim Erstellen von A.dll beim exportiert und importiert von B.dll (oder einen anderen Client) verwendet.

Diese Art von Überlagerung kann nicht durchgeführt werden, bei Verwendung die integrierten **AFX_EXT_CLASS** und `_AFXEXT` Präprozessorsymbole. Das oben beschriebene Verfahren löst dieses Problem in einer Weise, die nicht im Gegensatz zu die der Mechanismus MFC selbst verwendet werden soll, wenn dessen Active Technologien, die Datenbank und die Netzwerk-MFC-Erweiterungs-DLLs zu erstellen.

## <a name="not-exporting-the-entire-class"></a>Nicht exportieren die gesamte Klasse

Wenn Sie keine ganze Klasse exportieren, müssen Sie sicherstellen, dass die erforderlichen Datenelemente, die von den MFC-Makros erstellt ordnungsgemäß exportiert werden. Dies ist möglich durch Neudefinieren `AFX_DATA` in Ihre spezifische Klasse-Makro. Dies soll jedes Mal erfolgen Sie nicht die gesamte Klasse exportieren.

Zum Beispiel:

```
/* A.H */
#ifdef A_IMPL
   #define CLASS_DECL_A  _declspec(dllexport)
#else
   #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
   DECLARE_DYNAMIC()
   CLASS_DECL_A int SomeFunction();
   //... class definition ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)

- [Exportieren Sie aus einer DLL. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Bestimmen Sie die Exportmethode verwendet werden](../build/determining-which-exporting-method-to-use.md)

- [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)

### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Die LIB-Dienstprogramm und die/DEF-option](../build/reference/lib-reference.md)

## <a name="see-also"></a>Siehe auch

[Importieren und Exportieren](../build/importing-and-exporting.md)