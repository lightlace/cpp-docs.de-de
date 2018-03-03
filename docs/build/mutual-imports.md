---
title: Gegenseitige Importe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfd31cd4e5776555137daf002c076e14d4031f89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mutual-imports"></a>Gegenseitige Importe
Exportieren oder Importieren in eine andere ausführbare Datei birgt Komplikationen, wenn die Importe gegenseitig (oder zirkulär) sind. Zwei DLLs gibt z. B. importieren Symbole wechselseitig rekursive Funktionen ähnlich wie voneinander.  
  
 Das Problem bei gegenseitig importierende ausführbare Dateien (normalerweise DLLs) ist, dass keiner der beiden erstellt werden kann, ohne zuerst die andere erstellt. Jeder Buildprozess erfordert als Eingabe, eine Importbibliothek, die von der Build-Prozess erzeugt.  
  
 Die Lösung besteht darin, die LIB-Dienstprogramm mit der Option/DEF verwenden, die Importbibliothek erzeugt wird, ohne die ausführbare Datei erstellen. Mit diesem Dienstprogramm können Sie erstellen, alle Importbibliotheken, die Sie benötigen, unabhängig davon, wie viele DLLs beteiligt sind, oder wie kompliziert die Abhängigkeiten vorhanden sind.  
  
 Die Lösung im allgemeine für die Behandlung von gegenseitiger Imports ist:  
  
1.  Nehmen Sie wiederum jede DLL-Datei. (Beliebiger Reihenfolge ist dies möglich, obwohl einige Aufträge besser geeignet sind.) Wenn alle benötigten Importbibliotheken vorhanden und aktuell sind, führen die Verknüpfung, um die ausführbare Datei (DLL) zu erstellen. Dadurch wird eine Importbibliothek erzeugt. Führen Sie andernfalls LIB, um eine Importbibliothek zu erzeugen.  
  
     Ausführen von LIB mit der DEF-Option erstellt eine zusätzliche Datei mit ein. EXP-Erweiterung. Die. EXP-Datei muss später verwendet werden, um die ausführbare Datei zu erstellen.  
  
2.  Nach dem Erstellen aller Importbibliotheken mithilfe von LINK oder LIB, wechseln Sie zurück, und führen Sie die Verknüpfung, um alle ausführbaren Dateien zu erstellen, die nicht im vorherigen Schritt erstellt wurden. Beachten Sie, dass die entsprechende .exp-Datei in der Zeile LINK muss angegeben werden.  
  
     Wenn Sie das Dienstprogramm "LIB" weiter oben, um eine Importbibliothek für DLL1 zu erzeugen ausführen mussten, würde LIB sowie für die Datei DLL1.exp erstellt haben. Sie müssen als Eingabe für LINK DLL1.dll erstellen von DLL1.exp verwenden.  
  
 Die folgende Abbildung zeigt eine Lösung für zwei sich gegenseitig importierende DLLs, DLL1 und DLL2. Schritt 1 wird die DEF-Option festgelegt ist, auf DLL1 LIB ausgeführt. Schritt 1 erzeugt DLL1.lib, einer Importbibliothek und DLL1.exp. In Schritt 2 dient die Importbibliothek DLL2 zu erstellen, der wiederum eine Importbibliothek für von DLL2 erzeugt. Schritt 3 erstellt DLL1, mithilfe der DLL1.exp und DLL2.lib als Eingabe an. Beachten Sie, dass eine .exp-Datei für DLL2 nicht erforderlich ist, da LIB nicht zum Erstellen DLL2s Importbibliothek verwendet wurde.  
  
 ![Mithilfe von gegenseitigen Importen verknüpft zwei DLLs](../build/media/vc37yj1.gif "vc37YJ1")  
Verknüpfen von zwei DLLs mit gegenseitigen Importen  
  
## <a name="limitations-of-afxext"></a>Einschränkungen von _AFXEXT  
 Sie können die `_AFXEXT` Präprozessorsymbol für die MFC-Erweiterungs-DLLs, solange Sie nicht mehrere Ebenen von MFC-Erweiterungs-DLLs haben. Bei MFC-Erweiterungs-DLLs, die aufrufen oder eine Ableitung von Klassen in Ihrem eigenen MFC-Erweiterungs-DLLs, die dann von MFC-Klassen abgeleitet werden, müssen Sie eigene Präprozessorsymbol verwenden, um Mehrdeutigkeiten zu vermeiden.  
  
 Das Problem besteht darin, in Win32, müssen Sie alle Daten als explizit deklarieren **__declspec(dllexport)** wird jedoch aus einer DLL exportiert werden sollen und **von "__declspec(dllimport)" "** wird jedoch aus einer DLL importiert werden. Wenn Sie definieren `_AFXEXT`, die MFC-Header verwenden, stellen sicher, dass **AFX_EXT_CLASS** ordnungsgemäß definiert ist.  
  
 Wenn Sie haben mehrere Ebenen, ein Symbol wie z. B. **AFX_EXT_CLASS** ist nicht ausreichend, da eine MFC-Erweiterungs-DLL kann werden neue Klassen exportieren als auch andere Klassen von einem anderen MFC-Erweiterungs-DLL importieren. Um dieses Problem zu beheben, verwenden Sie ein spezielles Präprozessorsymbol, das angibt, dass Sie die DLL im Vergleich zum Verwenden der DLL erstellen. Nehmen Sie z. B., MFC-Erweiterungs-DLLs, A.dll und B.dll. Jeder exportieren bzw. einige Klassen in A.h bzw. B.h. B.dll verwendet die Klassen von A.dll. Die Headerdateien würde etwa wie folgt aussehen:  
  
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
  
 Wenn a.dll wird er basiert `/D A_IMPL` und wenn B.dll erstellt wird, wird es anhand erstellt `/D B_IMPL`. Durch die Verwendung separater Symbole für jede DLL-Datei `CExampleB` wird exportiert und `CExampleA` wird beim Erstellen von B.dll importiert. `CExampleA`Beim Erstellen von A.dll exportiert und importiert, wenn von B.dll (oder einem anderen Client) verwendet wird.  
  
 Diese Art der Schichtung kann nicht durchgeführt werden, bei Verwendung die integrierten **AFX_EXT_CLASS** und `_AFXEXT` Präprozessorsymbole. Die oben beschriebene Technik löst dieses Problem in einer Weise, die nicht im Gegensatz zum, die Mechanismus MFC selbst verwendet werden soll, wenn seine Active-Technologien, die Datenbank und die Netzwerk-MFC-Erweiterungs-DLLs zu erstellen.  
  
## <a name="not-exporting-the-entire-class"></a>Nicht exportieren die gesamte Klasse  
 Wenn Sie eine gesamte Objektklasse nicht exportieren, müssen Sie sicherstellen, dass die erforderlichen Datenelemente, die von der MFC-Makros erstellt ordnungsgemäß exportiert werden. Dies kann geschehen, indem Neudefinieren `AFX_DATA` Makro für Ihre spezifische Klasse. Diese Einstellung sollte jedes Mal vorgenommen werden Sie nicht die gesamte Klasse exportieren.  
  
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
  
-   [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)  
  
-   [Exportieren Sie aus einer DLL verwenden. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Welche Exportmethode ermitteln](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Die LIB-Dienstprogramm und die DEF-option](../build/reference/lib-reference.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren und Exportieren](../build/importing-and-exporting.md)