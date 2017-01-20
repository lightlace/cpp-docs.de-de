---
title: "Gegenseitige Importe"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AFXEXT-Präprozessorsymbol"
  - "AFX_DATA"
  - "AFX_EXT_CLASS-Makro"
  - "Zirkuläre Importe"
  - "DLLs [C++], Importieren"
  - "Ausführbare Dateien [C++], Importieren"
  - "Exportieren von DLLs [C++], Gegenseitige Importe"
  - "Erweiterungs-DLLs [C++], Gegenseitige Importe"
  - "Importieren von DLLs [C++], Gegenseitige Importe"
  - "Gegenseitige DLL-Importe [C++]"
  - "Gegenseitig importierende ausführbare Dateien [C++]"
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Gegenseitige Importe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Exportieren aus bzw. das Importieren in eine andere ausführbare Datei bringt Komplikationen mit sich, wenn die Importe gegenseitig \(oder zirkulär\) sind.  Wenn beispielsweise zwei DLLs Symbole untereinander importieren, ist dies mit gegenseitigen, rekursiven Funktionen vergleichbar.  
  
 Das Problem bei gegenseitig importierenden ausführbaren Dateien \(gewöhnlich DLLs\) besteht darin, dass keine der beiden Dateien erstellt werden kann, ohne dass zuerst die andere erstellt wurde.  Jeder Buildprozess erfordert eine Importbibliothek als Eingabe, die im jeweils anderen Buildprozess generiert wurde.  
  
 Die Lösung besteht darin, das LIB\-Dienstprogramm mit der **\/DEF**\-Option auszuführen. Durch dieses Dienstprogramm wird eine Importbibliothek ohne ausführbare Datei erstellt.  Mit diesem Dienstprogramm können Sie alle benötigten Importbibliotheken erstellen, unabhängig davon, wie viele DLLs beteiligt oder wie kompliziert die Abhängigkeiten sind.  
  
 Eine Lösung zur Handhabung gegenseitiger Importe sieht folgendermaßen aus:  
  
1.  Bearbeiten Sie die DLLs der Reihe nach. \(Obwohl bestimmte Reihenfolgen vorteilhafter sind, ist die Reihenfolge im Prinzip unerheblich.\) Wenn alle benötigten Importbibliotheken vorhanden und aktuell sind, führen Sie LINK aus, um die ausführbare Datei \(DLL\) zu erstellen.  Dadurch wird eine Importbibliothek generiert.  Andernfalls führen Sie LIB aus, um eine Importbibliothek zu erstellen.  
  
     Durch Ausführen von LIB mit der **\/DEF**\-Option wird eine zusätzliche Datei mit der Erweiterung EXP generiert.  Diese EXP\-Datei muss später zum Erstellen der ausführbaren Datei verwendet werden.  
  
2.  Nachdem Sie sämtliche Importbibliotheken entweder mit LINK oder LIB erstellt haben, führen Sie LINK erneut aus, um die ausführbaren Dateien zu erstellen, die im vorherigen Schritt nicht erstellt wurden.  Beachten Sie, dass die entsprechende EXP\-Datei in der LINK\-Befehlszeile angegeben werden muss.  
  
     Wenn Sie das LIB\-Dienstprogramm zu einem früheren Zeitpunkt ausgeführt hätten, um eine Importbibliothek für DLL1 zu erzeugen, hätte LIB die Datei DLL1.exp ebenfalls erstellt.  DLL1.exp muss beim Erstellen von DLL1.dll als Eingabe für LINK verwendet werden.  
  
 Die folgende Illustration zeigt eine Lösung für zwei sich gegenseitig importierende DLLs, DLL1 und DLL2.  In Schritt 1 wird LIB mit der **\/DEF**\-Option für **DLL1** ausgeführt.  In Schritt 1 wird die Importbibliothek DLL1.lib sowie DLL1.exp generiert.  In Schritt 2 wird die Importbibliothek verwendet, um **DLL2** zu erstellen, wodurch wiederum eine Importbibliothek für die Symbole von **DLL2** generiert wird.  In Schritt 3 werden DLL1.exp und DLL2.lib als Eingabe verwendet, um DLL1 zu erstellen.  Beachten Sie, dass für DLL2 keine EXP\-Datei erforderlich ist, da LIB nicht zum Erstellen der Importbibliothek von DLL2 verwendet wurde.  
  
 ![Zwei DLLs werden mithilfe von gegenseitigen Importen verknüpft](../build/media/vc37yj1.png "vc37YJ1")  
Verknüpfen von zwei DLLs mit gegenseitigen Importen  
  
## Einschränkungen von \_AFXEXT  
 Das `_AFXEXT`\-Präprozessorsymbol kann für Erweiterungs\-DLLs verwendet werden, solange die Erweiterungs\-DLLs nicht mehrschichtig angelegt sind.  Wenn Sie über Erweiterungs\-DLLs verfügen, die Klassen in Ihren eigenen Erweiterungs\-DLLs aufrufen oder von darin enthaltenen Klassen ableiten und diese DLLs wiederum von MFC\-Klassen abgeleitet werden, müssen Sie ein eigenes Präprozessorsymbol verwenden, um Mehrdeutigkeiten zu vermeiden.  
  
 Bei Win32 besteht das Problem darin, dass Sie alle Daten explizit als **\_\_declspec\(dllexport\)** deklarieren müssen, wenn sie aus einer DLL exportiert werden sollen, und als **\_\_declspec\(dllimport\)**, wenn sie aus einer DLL importiert werden sollen.  Wenn Sie `_AFXEXT` definieren, wird durch die MFC\-Header sichergestellt, dass **AFX\_EXT\_CLASS** korrekt definiert wird.  
  
 Bei Verwendung mehrerer Ebenen ist ein Symbol wie **AFX\_EXT\_CLASS** nicht ausreichend, da eine Erweiterungs\-DLL sowohl neue Klassen exportieren als auch weitere Klassen aus einer anderen Erweiterungs\-DLL importieren kann.  Um dieses Problem zu beheben, verwenden Sie ein spezielles Präprozessorsymbol, das angibt, dass Sie die DLL erstellen und nicht verwenden.  Angenommen, Sie verfügen über die beiden Erweiterungs\-DLLs A.dll und B.dll.  Beide exportieren einige Klassen in A.h bzw. B.h.  B.dll verwendet die Klassen von A.dll.  Die Headerdateien würden in etwa wie folgt aussehen:  
  
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
  
 A.dll wird mit `/D A_IMPL`, B.dll mit `/D B_IMPL` erstellt.  Indem separate Symbole für jede DLL verwendet werden, wird `CExampleB` beim Erstellen von B.dll exportiert und `CExampleA` importiert.  `CExampleA` wird beim Erstellen von A.dll exportiert und importiert, wenn es von B.dll oder einem anderen Client verwendet wird.  
  
 Diese Art der Schichtung wird nicht implementiert, wenn Sie die integrierten Präprozessorsymbole **AFX\_EXT\_CLASS** und `_AFXEXT` verwenden.  Mit der oben beschriebenen Technik wird das Problem auf eine Weise gelöst, die dem Mechanismus ähnelt, der von MFC beim Erstellen von Erweiterungs\-DLLs für Active Technology, Datenbanken und Netzwerke verwendet wird.  
  
## Kein Exportieren der gesamten Klasse  
 Wenn Sie keine gesamte Klasse exportieren, müssen Sie sich vergewissern, dass die durch die MFC\-Makros erstellten, erforderlichen Datenelemente korrekt exportiert werden.  Dazu können Sie `AFX_DATA` als Makro für Ihre spezifische Klasse neu definieren.  Die Neudefinition ist jedes Mal erforderlich, wenn Sie nicht die gesamte Klasse exportieren.  
  
 Beispiel:  
  
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
  
### Was möchten Sie tun?  
  
-   [Aus einer DLL exportieren](../build/exporting-from-a-dll.md)  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Das LIB\-Dienstprogramm und die \/DEF\-Option](../build/reference/lib-reference.md)  
  
## Siehe auch  
 [Importieren und Exportieren](../build/importing-and-exporting.md)