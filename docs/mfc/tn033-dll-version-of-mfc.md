---
title: "TN033: DLL-Version der MFC"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL-Bibliothek"
  - "DLL-Version der MFC [C++]"
  - "DLLs [C++], MFC"
  - "MFC-DLLs [C++], Schreiben von Erweiterungs-DLLs"
  - "TN033"
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# TN033: DLL-Version der MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis wird beschrieben, wie die gemeinsam genutzten Dynamic Link Librarys MFCxx.DLL oder MFCxxD.DLL \(wobei x für die MFC\-Versionsnummer steht\), mit MFC\-Anwendungen und Erweiterungs\-DLLs verwendet werden können.  Weitere Informationen über reguläre DLLs, finden Sie unter [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
 Dieser technische Hinweis enthält drei Aspekte von DLLs.  Die letzten beiden sind für die mehr fortgeschrittenen Benutzer:  
  
-   [Wie Sie eine MFC\-Erweiterungs\-DLL erstellen](#_mfcnotes_how_to_write_an_mfc_extension_dll)  
  
-   [Wie Sie eine MFC\-Anwendung erstellen, die die DLL\-Version von MFC verwendet](#_mfcnotes_writing_an_application_that_uses_the_dll_version)  
  
-   [Wie die MFC gemeinsam genutzten Dynamic Link Libraries\) implementiert werden](#_mfcnotes_how_the_mfc30.dll_is_implemented)  
  
 Wenn Sie mit der Erstellung interessiert sind, die, DLL mit MFC, das mit Nicht\-MFC\-Anwendungen \(diese eine reguläre DLL aufgerufen wird\) verwendet werden kann, finden Sie unter [Technischer Hinweis 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
## Übersicht über MFCxx.DLL\-Unterstützung: Terminologie und Dateien  
 **Reguläre DLL**: Sie verwenden eine reguläre DLL, um eine eigenständige DLL mithilfe verschiedener der MFC\-Klassen zu erstellen.  Schnittstellen über der App\-\/DLLgrenze sind "C Schnittstellen, und die Clientanwendung muss keine MFC\-Anwendung sein.  
  
 Dies ist die Version der DLL\-Unterstützung unterstützt in MFC 1.0.  Es wird in [Technischer Hinweis 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) beschrieben und die MFC Advanced Konzepte überprüfen [DLLScreenCap](../top/visual-cpp-samples.md).  
  
> [!NOTE]
>  Ab Visual C\+\+\-Version 4.0, ist der Begriff **USRDLL** veraltet und ist von einer regulären DLL ersetzt, die statisch mit MFC verknüpft.  Sie erstellen auch eine reguläre, dynamisch mit MFC verknüpften DLL.  
  
 MFC 3.0 \(und oben\) unterstützt regulären DLL mit allen neuen Funktionen einschließlich das OLE und Datenbankklassen.  
  
 **AFXDLL**: Dies wird auch als die freigegebene Version der MFC\-Bibliotheken.  Dies ist die neue DLL\-Unterstützung, die in MFC 2.0 hinzugefügt wird.  Die MFC\-Bibliothek selbst ist in mehreren DLLs \(nachfolgend beschrieben\) und eine Clientanwendung oder DLL verknüpft dynamisch die DLLs, die erforderlich sind.  Schnittstellen über der application\-\/DLLgrenze sind C\+\+\-\/MFCklassenschnittstellen.  Die Clientanwendung MUSS eine MFC\-Anwendung sein.  Dies unterstützt alle 3.0\-Funktionalität MFC \(Ausnahme: UNICODE wird nicht für die Datenbankklassen unterstützt\).  
  
> [!NOTE]
>  Ab Visual C\+\+\-Version 4.0, wird dieser DLL\-Typ als "Erweiterungs\-DLL."  
  
 Dieser MFCxx.DLL Hinweis verwendet, um den gesamten MFC\-DLL\-Satz zuzugreifen, der:  
  
-   Debuggen Sie: MFCxxD.DLL \(zusammen\) und MFCSxxD.LIB \(statisch\).  
  
-   Version: MFCxx.DLL \(zusammen\) und MFCSxx.LIB \(statisch\).  
  
-   Unicode debuggen: MFCxxUD.DLL \(zusammen\) und MFCSxxD.LIB \(statisch\).  
  
-   Unicode\-Version: MFCxxU.DLL \(zusammen\) und MFCSxxU.LIB \(statisch\).  
  
> [!NOTE]
>  Die Bibliotheken MFCSxx \[U\] \[D\] .LIB werden in Verbindung mit den MFC\-gemeinsamen genutzten DLLs verwendet.  Diese Bibliotheken enthalten Code, der zur Anwendung oder der DLL statisch verknüpft werden muss.  
  
 Links einer Anwendung zu den korrespondierenden Importbibliotheken:  
  
-   Debuggen Sie: MFCxxD.LIB  
  
-   Version: MFCxx.LIB  
  
-   Unicode debuggen: MFCxxUD.LIB  
  
-   Unicode\-Version: MFCxxU.LIB  
  
 "" Eine MFC\-Erweiterungs\-DLL ist eine DLL, die nach MFCxx.DLL erstellt wird \(und\/oder den anderen MFC\-gemeinsamengenutzten DLLs\).  Hier wird die MFC\-Teilarchitektur in.  Wenn Sie eine nützliche Klasse von eine MFC\-Klasse berechnen oder ein anderes vergleichbares Toolkit MFC erstellen, können Sie es in einer DLL speichern.  Diese DLL MFCxx.DLL verwendet, z, tut die endgültige Clientanwendung.  Damit können wiederverwendbare Arbeitsblattklassen, wiederverwendbare Basisklassen und wiederverwendbare Ansicht\/Dokumentklassen.  
  
## Vor\- und Nachteile  
 Warum sollten Sie die gemeinsam genutzte MFC\-Version verwenden?  
  
-   Verwenden der freigegebenen Bibliothek kann kleinere Anwendungen \(eine minimale Anwendung, die mit der MFC\-Bibliothek sehr kleiner als 10K ist\) führen.  
  
-   Die gemeinsam genutzte Version von MFC unterstützt MFC\-Erweiterungs\-DLLs und \-reguläre DLL.  
  
-   Eine Anwendung, die die freigegebenen MFC\-Bibliotheken verwendet, schneller ist als eine, statisch verknüpften MFC\-Anwendung erstellt, da es nicht notwendig ist, MFC selbst zu verknüpfen.  Dies ist in **DEBUGGEN** Builds insbesondere, bei denen der Linker die Debuginformationen komprimieren muss \- durch das Verknüpfen mit einer DLL, die bereits Debuginformationen enthält, gibt es weniger Debuginformationen, um innerhalb der Anwendung zu komprimieren.  
  
 Warum Sie die gemeinsam genutzte Version von MFC nicht verwenden:  
  
-   Das bei einer Anwendung, die die freigegebene Bibliothek verwendet, erfordert, dass die Bibliothek MFCxx.DLL \(und andere\) mit dem Programm geliefert werden.  MFCxx.DLL ist frei wie viele DLLs verteilt werden, sie müssen jedoch die DLL noch im Setupprogramm installiert werden.  Außerdem müssen Sie das MSVCRTxx.DLL ausliefern, die die C\-Laufzeitbibliothek enthält, die vom Programm und auch von den MFC\-DLLs selbst verwendet wird.  
  
##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> Erstellen einer MFC\-Erweiterungs\-DLL schreibt  
 Eine MFC\-Erweiterungs\-DLL ist die enthaltene Klasse und Funktionen einer DLL, die geschrieben werden, um die Funktionalität der MFC\-Klassen zu verschönern.  Eine MFC\-Erweiterungs\-DLL verwendet die gemeinsam genutzten MFC\-DLLs wie eine Anwendung verwendet es, mit einigen zusätzlichen Überlegungen:  
  
-   Der Buildprozess entspricht dem Erstellen einer Anwendung ähnlich, die die freigegebenen MFC\-Bibliotheken mit einigen zusätzlichen Compiler\- und Linkeroptionen verwendet.  
  
-   Eine MFC\-Erweiterungs\-DLL hat nicht `CWinApp` abgeleiteten Klasse.  
  
-   Eine MFC\-Erweiterungs\-DLL muss spezielles `DllMain` bereitstellen.  Der Anwendungs\-Assistent stellt `DllMain` eine Funktion, die Sie ändern können.  
  
-   Eine MFC\-Erweiterungs\-DLL stellt normalerweise eine Initialisierungsroutine, **CDynLinkLibrary** zu erstellen, wenn die Erweiterungs\-DLL `CRuntimeClass` es oder Ressourcen in die Anwendung exportiert werden sollen.  Eine abgeleitete Klasse **CDynLinkLibrary** wird möglicherweise verwendet, wenn Daten pro Anwendung die Erweiterungs\-DLL beibehalten werden muss.  
  
 Diese Aspekte werden ausführlich beschrieben.  Sie können MFC erweiterte Konzeptbeispiel auch [DLLHUSK](../top/visual-cpp-samples.md) verweisen, da veranschaulicht:  
  
-   Erstellen einer Anwendung mit der freigegebenen Bibliotheken. \(DLLHUSK.EXE ist eine MFC\-Anwendung, die dynamisch mit den MFC\-Bibliotheken sowie zu anderen DLLs. verknüpft\)  
  
-   Erstellen einer MFC\-Erweiterungs\-DLL speichern. \(Beachten Sie die speziellen Flags wie `_AFXEXT`, die verwendet werden, wenn Sie eine Erweiterungs\-DLL erstellt\)  
  
-   Zwei Beispiele von MFC\-Erweiterungs\-DLLs.  Man wird die grundlegende Struktur einer MFC\-Erweiterungs\-DLL mit beschränkten Exporten \(TESTDLL1\) und das andere die Aufschluss an, die eine ganze Klassen \(TESTDLL2\) exportieren.  
  
 Sowohl die Clientanwendung und alle Erweiterungs\-DLLs die gleiche Version von MFCxx.DLL verwenden.  Sie sollten der Konvention folgen der MFC\-DLL und ein Debugbuild und Version des Einzelhandels \(\/release\) der Erweiterungs\-DLL bereitstellen.  Dieses ermöglicht Clientprogramme, beide erstellen und debuggen Releasebuild ihrer Anwendungen und verknüpfen sie mit dem entsprechenden debuggen oder Einzelhandelsversion aller DLLs.  
  
> [!NOTE]
>  Da C\+\+\-Namensergänzungs\- und dem Export, die Exportliste einer Erweiterungs\-DLL können zwischen im Debug\- und im Releasebuild derselben DLL bzw. in DLLs für unterschiedliche Plattformen Unterschiede sind.  Das Releasebuild MFCxx.DLL hat ca. 2000 exportierte Einstiegspunkte; die Debug\- MFCxxD.DLL hat ca. 3000 exportierte Einstiegspunkte.  
  
### Schneller Hinweis Speicherverwaltung  
 Der Abschnitt, der "Speicherverwaltung," neben Ende dieses technischen Hinweises Securing wird, beschreibt die Implementierung des MFCxx.DLL mit der gemeinsam genutzten MFC\-Version.  Die Informationen, die Sie kennen müssen, um nur eine Erweiterungs\-DLL zu implementieren, werden hier beschrieben.  
  
 MFCxx.DLL und alle Erweiterungs\-DLLs, die in den Adressbereich einer Clientanwendung geladen werden, verwenden dieselbe Speicherbelegungsfunktion, dasselbe Ladeverfahren für Ressourcen und weitere "globale" MFC\-Zustände, als ob sie in derselben Anwendung enthalten wären.  Dies ist von Bedeutung, da MFC\-fremde DLL\-Bibliotheken und \-reguläre DLL, die statisch mit MFC verknüpfen, genau entgegengesetzt verfahren und jede DLL haben, die aus ihrem eigenen Bestand.  
  
 Wenn eine Erweiterungs\-DLL Speicher belegt, kann dieser Speicherbereich beliebig mit jedem anderen Objekt frei vermischen.  Wenn eine Anwendung, die die freigegebenen MFC\-Bibliotheken verwendet, abstürzt, behält der Schutz des Betriebssystems die Integrität anderer MFC\-Anwendungen, die die DLL ebenfalls nutzen.  
  
 Entsprechend werden andere "globale" MFC\-Zustände, wie die aktuelle ausführbare Datei, aus der Ressourcen geladen werden, auch von der Clientanwendung und allen MFC\-Erweiterungs\-DLLs sowie MFCxx.DLL selbst freigegeben.  
  
### Erstellen einer Erweiterungs\-DLL  
 Mit Anwendungs\-Assistenten verwenden, um ein MFC\-Erweiterungs\-DLL\-Projekt zu erstellen, und es generiert automatisch die passenden Compiler\- und Linkereinstellungen.  Es war generiert auch `DllMain` eine Funktion, die Sie ändern können.  
  
 Wenn Sie ein vorhandenes Projekt in einer MFC\-Erweiterungs\-DLL konvertieren, ordnet Anfang mit dem Standard für eine Anwendung mithilfe der gemeinsam genutzten MFC\-Version an, führt Folgendes:  
  
-   Fügen Sie **\/D\_AFXEXT** des Compilerflags hinzu.  Auf den Projekteigenschaften Akzeptieren Sie, wählen Sie den C\/C\+\+\-Knoten aus.  Wählen Sie dann die Präprozessorkategorie aus.  Fügen Sie `_AFXEXT` dem definierens\-Makrofeld hinzu und einzelnen Elemente mit Semikolons trennen.  
  
-   Entfernen Sie den **\/Gy** \- Compilerschalter.  Auf den Projekteigenschaften Akzeptieren Sie, wählen Sie den C\/C\+\+\-Knoten aus.  Wählen Sie dann die Codegenerierungskategorie aus.  Stellen Sie sicher, dass "die Funktion\-Ebene, aktivieren Sie die Option" verknüpft, ist nicht aktiviert.  Dies erleichtert es, Klassen zu exportieren, da der Linker nicht auf Features entfernt.  Wenn das ursprüngliche Projekt, eine reguläre DLL erstellt wird, die statisch mit MFC verknüpft ist, ändern Sie die Compileroption **\/MT\[d\]** in **\/MD\[d\]**.  
  
-   Erstellen Sie eine Exportbibliothek mit der Option **\/DLL** an LINK.  Dadurch wird festgelegt, wenn Sie ein neues Ziel erstellen und gibt Win32\-DynamicLink Library als der Zieltyp angezeigt.  
  
### Ändern der Headerdateien  
 Das Ziel einer Erweiterungs\-DLL ist normalerweise, einige allgemeine Funktionen in eine oder mehrere Anwendungen zu exportieren, die diese Funktionalität verwenden können.  Dies kocht unten zum Exportieren von Klassen und den globalen Funktionen, die die für Clientanwendungen verfügbar sind.  
  
 Hierzu müssen Sie Befolgung jede der Memberfunktionen als Importieren oder Exportieren entsprechend markiert ist.  Dies erfordert spezielle Deklarationen: **\_\_declspec \(dllexport\)** und **\_\_declspec \(dllimport\)**.  Wenn die Klassen mit Clientanwendungen verwendet werden, können Sie sie als **\_\_declspec \(dllimport\)** deklariert werden.  Wenn die Erweiterungs\-DLL selbst erstellt wird, sollten sie als **\_\_declspec \(dllexport\)** deklariert werden.  Außerdem müssen die Funktionen tatsächlich exportiert werden, sodass die Clientprogramme ihnen zur Ladezeit binden.  
  
 Um die ganze Klasse zu exportieren, verwenden Sie **AFX\_EXT\_CLASS** in die Klassendefinition.  Dieses Makro wird durch das Framework als **\_\_declspec \(dllexport\)** definiert, und `_AFXEXT`, wenn **\_AFXDLL** definiert ist, definiert jedoch als **\_\_declspec \(dllimport\)**, wenn `_AFXEXT` nicht definiert wird.  `_AFXEXT`, wie oben beschrieben, wird nur definiert, wenn die Erweiterungs\-DLL erstellt.  Beispiel:  
  
```  
class AFX_EXT_CLASS CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
### Kein Exportieren der gesamten Klasse  
 Manchmal möchten Sie nur die einzelnen erforderlichen Member der Klasse exportieren.  Möglicherweise benötigen Sie beim Exportieren einer von `CDialog` abgeleiteten Klasse z. B. nur den Konstruktor und den `DoModal`\-Aufruf.  Sie können diese Member exportiert, welche das die DEF\-Datei der DLL verwenden, aber Sie können **AFX\_EXT\_CLASS** für einzelne Member auch auf ähnliche Weise verwenden, die Sie exportieren müssen.  
  
 Beispiel:  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   // rest of class definition  
   .  
   .  
   .  
};  
```  
  
 Wenn Sie dies tun, werden möglicherweise auf ein zusätzliches Problem ausgeführt, da Sie nicht mehr alle Member der Klasse exportieren.  Das Problem ist auf die Art, von MFC\-Makros.  Es gibt derzeit verschiedene MFC\-Hilfsmakros, durch die Datenmember deklariert oder definiert werden.  Daher müssen diese Datenmember auch aus der DLL exportiert werden.  
  
 Das `DECLARE_DYNAMIC`\-Makro wird beim Erstellen einer Erweiterungs\-DLL z. B. wie folgt definiert:  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
   public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
 Die Zeile, die statisches " `AFX_DATA`" beginnt, deklariert ein statisches Objekt innerhalb einer Klasse.  Um diese Klasse korrekt zu exportieren und auf die Laufzeitinformationen von einem Client .EXE\-Verarbeitungsoptionen zuzugreifen, müssen Sie dieses statische Objekt exportieren.  Da das statische Objekt mit dem `AFX_DATA`\-Modifizierer deklariert wird, müssen Sie `AFX_DATA` beim Erstellen der DLL einfach als **\_\_declspec\(dllexport\)** und beim Erstellen des ausführbaren Clients als **\_\_declspec\(dllimport\)** definieren.  
  
 Wie oben erläutert, wird **AFX\_EXT\_CLASS** bereits auf diese Art definiert.  Sie müssen nur `AFX_DATA` neu definieren, um der Kontext der Klassendefinition **AFX\_EXT\_CLASS** entspricht zu sein.  
  
 Beispiel:  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
class CExampleView : public CView  
{  
  DECLARE_DYNAMIC()  
  // ... class definition ...  
};  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 MFC verwendet stets das `AFX_DATA` \- Symbol für Datenelemente, die innerhalb der Makros definiert, daher funktioniert diese Technik für all diese Szenarien.  Beispielsweise funktioniert es für `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Wenn Sie anstelle ausgewählter Klassenmember die gesamte Klasse exportieren, werden statische Datenmember automatisch exportiert.  
  
 Sie können das gleiche Verfahren verwenden, den `CArchive` Extraktionsoperator für Klassen automatisch zu exportieren, die Makros `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` verwenden.  Exportieren des Archivoperator, indem Sie die Klassendeklarationen markieren \(in. .h\-Datei\) mit dem folgenden Code:  
  
```  
#undef AFX_API  
#define AFX_API AFX_EXT_CLASS  
  
<your class declarations here>  
  
#undef AFX_API  
#define AFX_API  
```  
  
### Einschränkungen von \_AFXEXT  
 Sie können das **AFXEXT** \_Präprozessorsymbol für Erweiterungs\-DLLs verwenden, sofern Sie nicht mehrere Ebenen Erweiterungs\-DLLs verfügen.  Wenn Sie über Erweiterungs\-DLLs verfügen, die Klassen in Ihren eigenen Erweiterungs\-DLLs aufrufen oder von darin enthaltenen Klassen ableiten und diese DLLs wiederum von MFC\-Klassen abgeleitet werden, müssen Sie ein eigenes Präprozessorsymbol verwenden, um Mehrdeutigkeiten zu vermeiden.  
  
 Bei Win32 besteht das Problem darin, dass Sie alle Daten explizit als **\_\_declspec\(dllexport\)** deklarieren müssen, wenn sie aus einer DLL exportiert werden sollen, und als **\_\_declspec\(dllimport\)**, wenn sie aus einer DLL importiert werden sollen.  Wenn Sie `_AFXEXT` definieren, wird durch die MFC\-Header sichergestellt, dass **AFX\_EXT\_CLASS** korrekt definiert wird.  
  
 Wenn Sie mehrere Ebenen verfügen, ist ein Symbol wie **AFX\_EXT\_CLASS** nicht ausreichend, da eine Erweiterungs\-DLL sowohl neue Klassen exportieren als auch weitere Klassen aus einer anderen Erweiterungs\-DLL importieren.  Um dieses Problem zu lösen ein spezielles Präprozessorsymbol, das angibt dass Sie die DLL selbst mit der DLL erstellen.  Angenommen, Sie verfügen über die beiden Erweiterungs\-DLLs A.DLL und B.DLL vor.  Sie jeder Export einige Klassen in A.H und in B.H, bzw.  B.DLL verwendet die Klassen von A.DLL.  Die Headerdateien würden in etwa wie folgt aussehen:  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A   __declspec(dllexport)  
#else  
   #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
  
/* B.H */  
#ifdef B_IMPL  
   #define CLASS_DECL_B   __declspec(dllexport)  
#else  
   #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition .. };  
```  
  
 Wenn A.DLL erstellt wird, wird es mit **\/D A\_IMPL** erstellt und wenn B.DLL erstellt wird, wird es mit **\/D B\_IMPL** erstellt.  Indem separate Symbole für jede DLL verwendet, wird CExampleB exportiert und CExampleA wird importiert, wenn Sie B.DLL erstellt.  CExampleA exportiert, wird, wenn von A.DLL erstellt und importiert, wenn es von B.DLL verwendet wird \(oder einen anderen Client\).  
  
 Diese Art der Schichtung wird nicht implementiert, wenn Sie **AFX\_EXT\_CLASS** und die integrierte `_AFXEXT` Präprozessorsymbole verwendet.  Die Technik, die oben beschrieben wird, wird das Problem auf eine Weise gelöst nicht anders die dem Mechanismus MFC selbst, wenn sie die Datenbank\-, OLE\- und Netzwerke verwendet wird.  
  
### Kein Exportieren der gesamten Klasse  
 Möglicherweise sollten Sie insbesondere darauf achten, wenn Sie keine gesamte Klasse exportieren.  Sie müssen sicherstellen, dass die erforderlichen Datenelemente, die durch die MFC\-Makros erstellten, korrekt exportiert werden.  Dies kann erfolgen, indem **AFX\_DATA** \-Makro für Ihre spezifische Klasse neu definiert.  Die Neudefinition ist jedes Mal erforderlich, wenn Sie nicht die gesamte Klasse exportieren.  
  
 Beispiel:  
  
```  
// A.H  
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
   //class definition   
   .  
   .  
   .  
};  
  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### DllMain  
 Es folgt der genaue Code, den Sie in der Hauptquelldatei für die Erweiterungs\-DLL legen sollten.  Es sollte stammen nachdem die Standardeinschließung.  Beachten Sie, dass, wenn Sie Anwendungs\-Assistenten verwenden, um Startdateien für eine Erweiterungs\-DLL zu erstellen, diese `DllMain` für Sie angibt.  
  
```  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE extensionDLL;  
  
extern "C" int APIENTRY   
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      // Extension DLL one-time initialization   
      if (!AfxInitExtensionModule(  
             extensionDLL, hInstance))  
         return 0;  
  
      // TODO: perform other initialization tasks here  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      // Extension DLL per-process termination  
      AfxTermExtensionModule(extensionDLL);  
  
          // TODO: perform other cleanup tasks here  
   }  
   return 1;   // ok  
}  
```  
  
 Der Aufruf von `AfxInitExtensionModule` wird die Modullaufzeitklassen Strukturen \(`CRuntimeClass` \) sowie seine Object Factories \(`COleObjectFactory` \) für Objekte Verwendung später auf, wenn das **CDynLinkLibrary**\-Objekt erstellt wird.  Der \(optionale\) Aufruf von `AfxTermExtensionModule` kann MFC, um die Erweiterungs\-DLL bereinigen, sobald ein Prozess \(der wenn die bevor geschieht, oder wenn die DLL aufgrund eines **FreeLibrary** Aufrufs entladen wird\), von der Erweiterungs\-DLL getrennt wird.  Da die meisten Erweiterungs\-DLLs nicht dynamisch \(normalerweise, werden sie zu ihren Importbibliotheken verknüpft\), geladen werden, ist der Aufruf von `AfxTermExtensionModule` normalerweise nicht notwendig.  
  
 Wenn die Anwendung Erweiterungs\-DLLs dynamisch lädt und freigibt, stellen Sie sicher, ein `AfxTermExtensionModule` wie oben gezeigt aufzurufen.  Stellen Sie auch sicher, `AfxLoadLibrary` und `AfxFreeLibrary` zu verwenden \(anstelle der Win32\-Funktionen **LoadLibrary** und **FreeLibrary**\), wenn die Anwendung mehrere Threads verwendet, oder wenn sie eine Erweiterungs\-DLL dynamisch lädt.  Mit `AfxLoadLibrary` und `AfxFreeLibrary` stellt sicher, dass der Code für das Starten und Beenden, ausführt, wenn die Erweiterungs\-DLL geladen und entladen den globalen MFC\-Zustand nicht beschädigt.  
  
 Die Headerdatei AFXDLLX.H enthält spezielle Definitionen für Strukturen, die in Erweiterungs\-DLLs, wie die Definitionen für `AFX_EXTENSION_MODULE` und **CDynLinkLibrary** verwendet werden.  
  
 Das globale *extensionDLL* muss wie gezeigt deklariert werden.  Im Gegensatz zur 16\-Bit\-Version von MFC, können MFC\-Funktionen während dieser Zeit Speicher belegen und aufrufen, wie das MFCxx.DLL vollständig initialisiert ist, bis das `DllMain`.  
  
### Gemeinsame Nutzung von Ressourcen und Klassen  
 Einfachen Export der MFC\-Erweiterungs\-DLL\-Anforderung nur einige LOWBandbreitenfunktionen zur Clientanwendung und zu nichts mehr.  Mehr Benutzeroberfläche anspruchsvollen DLLs sollten Ressourcen und C\+\+\-Klassen in die Clientanwendung exportieren.  
  
 Der Export von Ressourcen erfolgt über eine Ressourcenliste.  In jeder Anwendung ist eine einfach verknüpfte Liste mit **CDynLinkLibrary**\-Objekten.  Wenn sie nach einer Ressource finden, betrachten die meisten MFC\-Standardimplementierungen, durch die Ressourcen geladen werden, zunächst im aktuellen Ressourcenmodul \(`AfxGetResourceHandle`\) und wenn er nicht ausgeführt wendet die Liste der **CDynLinkLibrary** gefunden wird, den ein Versuch, die angeforderte Ressource zu laden.  
  
 Die dynamische Erstellung von C\+\+\-Objekten, dass Klassennamen in C\+\+ erhalten, verläuft ähnlich.  Der Mechanismus zur Deserialisierung von MFC\-Objekten erfordert alle `CRuntimeClass`\-Objekte haben, die so registriert werden, damit er rekonstruieren kann, indem er dynamisch C\+\+\-Objekt des erforderlichen Typs anhand, der zuvor gespeichert wurde.  
  
 Wenn die Clientanwendung soll, Klassen in der Erweiterungs\-DLL verwenden, die `DECLARE_SERIAL` sind, müssen Sie die Klassen exportieren, um zur Clientanwendung sichtbar ist.  Dies wird auch ausgeführt, indem die **CDynLinkLibrary** Liste durchlaufen wird.  
  
 Im Fall der MFC Advanced Konzepte überprüfen Sie [DLLHUSK](../top/visual-cpp-samples.md), sieht die Liste etwa folgendermaßen aus:  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
               |                      |  
            MFC90D.DLL            MFC90.DLL  
```  
  
 Das MFCxx.DLL befindet sich in der Ressourcen\- und Klassenliste.  MFCxx.DLL schließt alle Ressourcen des Standardanbieters MFC, einschließlich der Eingabeaufforderungen aller Standardbefehls\-IDs.  Das Platzieren er am Ende der Liste können DLLs und die Clientanwendung selbst, eine eigene Kopie der MFC\-Standardressourcen verfügen, jedoch auf die gemeinsam genutzten Ressourcen im MFCxx.DLL stattdessen zu verlassen.  
  
 Wenn Sie die Ressourcen und Klassennamen aller DLLs im Namespace der Clientanwendung hat den Nachteil, dass Sie darauf achten müssen, welche von IDs und Namen Sie auswählen.  Sie können diese Funktion jedoch deaktivieren, indem Sie nicht entweder die **CDynLinkLibrary** oder Ressourcen ein Objekt zur Clientanwendung exportieren.  Im [DLLHUSK](../top/visual-cpp-samples.md)\-Beispiel wird der Namespace für gemeinsam genutzte Ressourcen mithilfe mehrerer Headerdateien verwaltet.  [Technischer Hinweis 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) finden Sie weitere Tipps zur Verwendung von Dateien der freigegebenen Ressource.  
  
### Initialisieren der DLL  
 Wie bereits erwähnt werden Sie gewöhnlich ein **CDynLinkLibrary**\-Objekt erstellen, um die Ressourcen und Klassen in die Clientanwendung zu exportieren.  Sie müssen einen exportierten Einstiegspunkt angeben, um die DLL zu initialisieren.  Minimal liegt eine ungültige Routine, die keine Argumente akzeptiert und zurückgibt nichts, kann alle sein, das Sie wie.  
  
 Jede Clientanwendung, die die DLL verwenden möchte, muss diese Initialisierungsroutine aufrufen, wenn Sie diesen Ansatz verwenden.  Sie ordnen auch diesem **CDynLinkLibrary**\-Objekt im `DllMain` unmittelbar nach dem Aufrufen von `AfxInitExtensionModule`.  
  
 Die Initialisierungsroutine muss **CDynLinkLibrary** ein Objekt im aktuellen Heap der Anwendung erstellen, der bis zu den Erweiterungs\-DLL\-Informationen verkabelt ist.  Dies kann mit dem folgenden ausgeführt werden:  
  
```  
extern "C" extern void WINAPI InitXxxDLL()  
{  
   new CDynLinkLibrary(extensionDLL);  
}  
```  
  
 Der Routinename, *InitXxxDLL*, in diesem Beispiel kann beliebiger Wert sein, den Sie möchten.  Er muss nicht, um ein `extern "C"` handeln, das Damit wird so die Exportliste einfacher zu warten.  
  
> [!NOTE]
>  Wenn Sie die Erweiterungs\-DLL aus einer regulären DLL verwenden, müssen Sie diese Initialisierungsfunktion exportieren.  Vor Verwendung aller Erweiterungs\-DLL\-Klassen oder Ressourcen dieser Funktion muss den regulären DLL aufgerufen werden.  
  
### Exportieren von Einträgen  
 Die einfache Möglichkeit dar, die Klassen exportieren ist, **\_\_declspec \(dllimport\)** und **\_\_declspec \(dllexport\)** auf jeder Klasse und globalen Funktion verwenden, die Sie exportieren möchten.  Dies macht es einfacher, ist jedoch weniger effizient als, jeden Einstiegspunkt Benennungsprobleme \(nachfolgend beschrieben\) als Sie weniger Steuerelement verfügen darüber, welche Funktionen exportiert und Sie die Funktionen nicht anhand der Ordinalzahl exportiert werden können.  TESTDLL1 TESTDLL2 und verwenden diese Methode, um die Einträge zu exportieren.  
  
 Eine effizientere Methode \(und die Methode wird von MFCxx.DLL\) ist, alle Einträge von Hand zu exportieren, indem sie jeden Eintrag in der DEF\-Datei benennen.  Da wir selektive Exporte von der DLL, also nicht alle\) exportieren, müssen wir uns entscheiden, die bestimmte Schnittstellen Sie exportieren möchten.  Dies ist schwierig, da Sie den ergänzten Namen den Linker in Form von Einträgen in der DEF\-Datei angeben müssen.  Exportieren keine C\+\+\-Klassen, es sei denn, dass Sie tatsächlich einen symbolischen Link für ihn benötigen.  
  
 Wenn Sie versucht haben, C\+\+ Exportieren, sollten Klassen mit einem .DEF Datei vor, Sie entwickeln ein Tool, um diese Liste automatisch zu generieren.  Dies kann mit einem zweistufigen Verbindungsprozesses durchgeführt werden.  Verknüpfen Sie die DLL einmal ohne Exporte, und ermöglichen Sie den Linker, um eine .MAP\-Datei zu generieren.  Die .MAP\-Datei kann verwendet werden, um eine Liste von Funktionen zu generieren, die exportiert werden sollen, damit einige Neuanordnen, kann sie verwendet werden, um die EXPORT\-Einträge der DEF\-Datei zu generieren.  Der für Exportliste MFCxx.DLL und OLE und die Datenbankerweiterungs\-dlls, mehrere tausend zahlreich, wurde mit einem solchen Prozess generiert \(obwohl diese nicht automatisch eine vollständig ist und offensichtlich erfordert, die von Zeit zu Zeit\) optimiert.  
  
### CWinApp für CDynLinkLibrary  
 Eine MFC\-Erweiterungs\-DLL hat kein von `CWinApp` abgeleitetes Objekt von eigenen; Stattdessen muss sie mit `CWinApp` abgeleiteten Objekt der Clientanwendung arbeiten.  Dies bedeutet, dass die Clientanwendung die Haupt\-Meldungsverteilschleife im Besitz, die Leerlaufschleife usw.  
  
 Wenn die MFC\-Erweiterungs\-DLL spezielle Daten für jede Anwendung verwalten muss, können Sie eine neue Klasse von **CDynLinkLibrary** ableiten und in der InitXxxDLL\-Routine erstellen beschreiben Sie oben.  Die DLL kann dann bei ihrer Ausführung die Liste der **CDynLinkLibrary**\-Objekte der aktuellen Anwendung überprüfen, um das Objekt für die jeweilige Erweiterungs\-DLL zu suchen.  
  
### Verwenden von Ressourcen in der DLL Implementierung  
 Wie bereits erwähnt ist die Standardressourcelast die Liste der **CDynLinkLibrary** von Objekten, die dem ersten EXE oder nach der DLL, die, suchen die angeforderte Ressource verfügt.  Alle MFC\-APIs sowie alle mit `AfxFindResourceHandle` des internen Codes, die Ressourcenliste durchläuft, um eine Ressource zu suchen, unabhängig wo sie sich befindet.  
  
 Wenn Sie Ressourcen nur von einer bestimmten Stelle laden möchten, verwenden Sie die APIs `AfxGetResourceHandle` und `AfxSetResourceHandle`, um das alte Handle zu speichern und das neue Handle festzulegen.  Achten Sie darauf, dass Sie das alte Ressourcenhandle wiederherstellen, bevor Sie zur Clientanwendung zurückkehren.  Das Beispiel TESTDLL2 wird dieser Ansatz für ein Menü explizit laden.  
  
 Das Durchlaufen der Liste hat jedoch den Nachteil, dass die Suche etwas langsamer ist und dass die Ressourcen\-ID\-Bereiche verwaltet werden müssen.  Der Vorteil liegt darin, dass eine Clientanwendung, die mit mehreren Erweiterungs\-DLLs verknüpft ist, jede durch die DLL zur Verfügung gestellte Ressource nutzen kann, ohne dass das DLL\-Instanzenhandle angegeben werden muss.  `AfxFindResourceHandle` ist eine API, die bei der Suche nach einer bestimmten Übereinstimmung die Ressourcenliste durchläuft.  Sie verwendet den Ressourcennamen und \-typ als Parameter und gibt das zuerst ermittelte Ressourcenhandle \(oder NULL\) zurück.  
  
##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> Eine Anwendung schreiben, die die DLL Version verwendet  
  
### Anwendungs\-Anforderungen  
 Eine Anwendung, die die freigegebene Version von MFC verwendet, muss einigen einfachen Regeln beachten:  
  
-   Sie muss ein `CWinApp`\-Objekt verfügen und den Standardregeln für Nachrichtenzustellungssystem folgen.  
  
-   Sie muss mit einem Satz von erforderlichen Compilerflags kompiliert werden \(siehe unten\).  
  
-   Sie muss mit den MFCxx\-Importbibliotheken verknüpfen.  Indem festlegt, kennzeichnet der erforderliche Compiler, die MFC\-Header bestimmen Zeitpunkt der Verknüpfung, der Bibliothek die Anwendung beziehen sollte mit.  
  
-   So die ausführbare Datei ausführen sollen, muss MFCxx.DLL auf den Pfad oder in das Windows\-Systemverzeichnis.  
  
### Erstellen mit der Entwicklungsumgebung  
 Wenn Sie die interne Makefile mit die meisten Standardstandards verwenden, können Sie das Projekt mühelos ändern, die DLL\-Version zu erstellen.  
  
 Der folgende Schritt wird vorausgesetzt, dass eine ordnungsgemäß funktionierende MFC\-Anwendung verfügen, die mit NAFXCWD.LIB \(für Links wird, debuggen\) und \(für NAFXCW.LIB Releasebuild\) und Sie möchten diesen konvertieren, um die freigegebene Version der MFC\-Bibliothek zu verwenden.  Sie führen die Visual C\+\+\-Umgebung aus und eine interne Projektdatei.  
  
1.  **Projekte** Klicken Sie im Menü auf **Eigenschaften**.  Auf der Seite **Allgemein** unter **Projektstandards**, legen Sie Microsoft Foundation Classes auf **MFC in einer gemeinsam genutzten DLL verwenden** fest \(MFCxx \(D\) DLL\).  
  
### Erstellen mit NMAKE  
 Wenn Sie die externe Makefilefunktion Visual C\+\+ verwenden oder NMAKE direkt verwenden, müssen Sie die Makefile bearbeiten, um Compiler\- und Linkeroptionen unterstützen  
  
 Erforderliche Compilerflags:  
  
 **\/D\_AFXDLL \/MD**  
 **\/D\_AFXDLL**  
  
 Die Header standardmäßigen MFC benötigen dieses Symbol, definiert werden:  
  
 **\/MD**  
 Die Anwendung muss anhand DLL\-Version der C\-Laufzeitbibliothek verwenden  
  
 Alle anderen Compilerflags folgen den MFC\-Standards \(beispielsweise, debuggen \_DEBUG für\).  
  
 Bearbeiten Sie die Linkerliste Bibliotheken.  Ändern Sie NAFXCWD.LIB zu MFCxxD.LIB und ändern Sie NAFXCW.LIB zu MFCxx.LIB.  Ersetzen Sie LIBC.LIB durch MSVCRT.LIB.  Wie mit jeder anderen MFC\-Bibliothek ist es wichtig, dass MFCxxD.LIB eine **before** mit C\-Laufzeitbibliotheken ist.  
  
 Optional können Sie **\/D\_AFXDLL** dem Releasebuild hinzu und debuggen Sie Ressourcencompileroptionen \(die, die eigentlich die Ressourcen mit **\/R** kompiliert\).  Dies macht endgültigen ausführbares kleineres, indem Ressourcen freigibt, die in den MFC\-DLLs vorhanden sind.  
  
 Ein vollständige Neuerstellung erforderlich, nachdem diese Änderungen vorgenommen werden.  
  
### Erstellen der Beispiele  
 Die meisten MFC\-Beispielprogramme können von Visual C\+\+ oder einer freigegebenen NMAKE\-kompatiblen MAKEFILE von der Befehlszeile erstellt werden.  
  
 Um alle Beispiele zu konvertieren um MFCxx.DLL verwendet, können Sie die .MAK\-Datei in Visual C\+\+ und laden die Projektoptionen festlegen wie oben beschrieben.  Wenn Sie den NMAKE\-Build verwenden, können Sie "AFXDLL\=1" auf der NMAKE\-Befehlszeile angeben und die erstellt das Beispiel mithilfe der freigegebenen MFC\-Bibliotheken.  
  
 Das erweiterte MFC Konzeptbeispiel [DLLHUSK](../top/visual-cpp-samples.md) wird mit der DLL\-Version von MFC erstellt.  In diesem Beispiel wird nicht nur, wie eine Anwendung erstellt, die mit MFCxx.DLL verknüpft werden, aber es wird auch weitere Funktionen der MFC\-DLL\-Verpackungsoption wie MFC\-Erweiterungs\-DLLs, die später in diesem technischen Hinweis beschrieben werden.  
  
### Verpackenhinweise  
 Die Einzelhandelsversion der DLLs \(MFCxx \[U\] .DLL\) können frei verteilt werden.  Die Debugversion der DLLs können nicht frei verteilt werden und sollten nur bei der Entwicklung der Anwendung verwendet werden.  
  
 Die Debugkonfiguration DLLs werden mit Debuginformationen bereitstellen.  Mit dem Visual C\+\+\-Debugger verwenden, können Sie die Ausführung der Anwendung sowie DLL aufzeichnen.  Die Versions\-DLLs \(MFCxx \[U\] .DLL\) enthalten keine Debuginformationen.  
  
 Wenn Sie oder neu erstellen die DLLs anpassen, sollten Sie sie leicht unterschiedlich "MFCxx," aufrufen, das die Datei MFCDLL.MAK MFC SRC Buildoptionen beschreibt und die Logik für das Umbenennen der DLL enthält.  Die Dateien umzubenennen ist notwendig, da diese DLLs durch viele MFC\-Anwendungen freigegeben sind.  Die benutzerdefinierte Version der MFC\-DLLs aufweist, ersetzen Sie die, die auf dem System installiert werden, kann eine andere MFC\-Anwendung mithilfe der gemeinsam genutzten MFC\-DLLs unterbrechen.  
  
 Das Neu erstellen der MFC\-DLLs wird nicht empfohlen.  
  
##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> Wie das MFCxx.DLL implementiert wird  
 Im folgenden Abschnitt wird beschrieben, wie die MFC\-DLL \(MFCxx.DLL und MFCxxD.DLL\) implementiert wird.  Verstehend sind die Details hier auch nicht wichtig, wenn ein beliebiges Element, das Sie ausführen, die MFC\-DLL, mit der Anwendung zu verwenden ist.  Die Details sind hier nicht zum Verständnis wichtig, wie eine MFC\-Erweiterungs\-DLL schreibt, aber das Verständnis dieser Implementierung können Ihnen, eigene DLL zu schreiben.  
  
### Implementierungs\-Übersicht  
 Die MFC\-DLL ist tatsächlich ein Sonderfall einer MFC\-Erweiterungs\-DLL, wie oben beschrieben.  Sie verfügt über eine sehr große Anzahl von Exporten für viele Klassen.  Es gibt verschiedene weitere Vorgänge, die, wird in der MFC\-DLL, die sie sogar speziell machen, als reguläre Erweiterungs\-DLL verwenden.  
  
### Win32 werden die meisten der Arbeit  
 Die 16\-Bit\-Version von MFC benötigt einige spezielle Verfahren einschließlich ProApp\-Daten auf dem Stapelsegment, besonderen Segmenten, die von Assemblycode entweder 80x86 erstellt wurden, den Ausnahmekontexten pro Prozess und anderen Techniken.  Win32 direkt unterstützt Daten auf Prozessbasis in einer DLL, ist die, was Sie der Regel werden.  In den meisten Fällen ist NAFXCW.LIB MFCxx.DLL nur, das in einer DLL gepackt.  Wenn Sie den MFC\-Quellcode berücksichtigen, suchen Sie sehr wenig \#ifdef \_AFXDLL, da es sehr wenige Sonderfälle gibt, die vorgenommen werden müssen.  Die Daten, die dort sind, sind speziell, Win32 unter Windows 3.1 zu verarbeiten \(andernfalls wird als Win32\).  Win32 unterstützt nicht DLL\-Daten pro Prozess direkt, daher muss die MFC\-DLL \(TLS\)\- die Win32 APIs des lokalen Threadspeicher verwenden, um Prozesslokale Daten abzurufen.  
  
### Auswirkungen auf Bibliotheks\-Quellen, weitere Dateien  
 Auswirkung der **\_AFXDLL**\-Version auf den normalen MFC\-Klassen\-Bibliotheksquellen und Header sind relativ klein.  Eine spezielle Versionsdatei \(AFXV\_DLL.H\) als auch eine zusätzliche Headerdatei \(AFXDLL\_.H\) eingeschlossen durch die Haupt\-AFXWIN.H\-Kopfzeile.  Die AFXDLL\_.H\-Kopfzeile schließt die **CDynLinkLibrary**\-Klasse und andere Implementierungsdetails von **\_AFXDLL**\-Anwendungen und OF MFC\-Erweiterungs\-DLLs ein.  Die AFXDLLX.H\-Kopfzeile wird zum Erstellen von MFC\-Erweiterungs\-DLLs bereitgestellt \(siehe oben für Details\).  
  
 Die regulären Quellen der MFC\-Bibliothek in MFC SRC haben einen Zusatzbedingungscode unter dem **\_AFXDLL** \#ifdef.  Eine zusätzliche Quelldatei \(DLLINIT.CPP\) enthält zusätzlichen den Initialisierungscode einer und anderen Kleber für die gemeinsam genutzte Version von MFC.  
  
 Um die gemeinsam genutzte MFC\-Version zu erstellen, sind zusätzliche Dateien bereitgestellt. \(Siehe unten Details darüber, wie die DLL erstellt.\)  
  
-   Zwei DEF\-Dateien werden zum Exportieren der MFC\-DLL\-Einstiegspunkte für Debuggen \(MFCxxD.DEF\) und freigeben Versionen \(MFCxx.DEF\) der DLL verwendet.  
  
-   Eine \(RC\-Datei MFCDLL.RC\) enthält alle Ressourcen des Standardanbieters MFC und eine VERSIONINFO\-Ressource für die DLL.  
  
-   Eine .CLW\-Datei \(MFCDLL.CLW\) wird bereitgestellt, um das Durchsuchen der MFC\-Klassen mithilfe des Klassen\-Assistenten zuzulassen.  Hinweis: diese Funktion ist nicht der DLL\-Version von MFC bestimmt.  
  
### Speicherverwaltung  
 Eine Anwendung mit MFCxx.DLL verwendet eine allgemeine Speicherbelegungsfunktion, die von MSVCRTxx.DLL, die freigegebene C\-Laufzeit DLL bereitgestellt wird.  Die Anwendung, alle Erweiterungs\-DLLs und gut als die MFC\-DLLs selbst verwenden diese freigegebene Speicherbelegungsfunktion.  Indem eine gemeinsam genutzte DLL für Speicherbelegung verwenden, können die MFC\-DLLs Speicherbelegung, die später von der Anwendung oder umgekehrt freigegeben wird.  Da die Anwendung und DLL dieselbe Zuweisung verwenden müssen, sollten Sie C\+\+ globales `operator new` oder `operator delete` nicht überschreiben.  Die gleichen Regeln gelten für den Rest der C\-Laufzeit\-Speicherbelegungsroutinen zu \(wie `malloc`, `realloc`, **free** usw.\).  
  
### Ordnungszahlen und Klasse \_\_declspec \(dllexport\) und DLL\-Benennung  
 Wir verwenden nicht die Funktionen `class` **\_\_declspec \(dllexport\)** des C\+\+\-Compilers.  Stattdessen wird eine Liste von Exporten mit den Klassenbibliotheksquellen enthalten \(MFCxx.DEF und MFCxxD.DEF\).  Nur dieses werden ausgewählten Satz Einstiegspunkte \(Funktionen und Daten\) exportiert.  Anderen Symbolen, wie private Implementierungsfunktionen oder \- klassen MFC, werden nicht alle Exporte werden durchgeführt nach Ordnungszahl ohne einen Zeichenfolgennamens im Menschen ansässigen oder nicht in der Namentabelle exportiert.  
  
 Die Verwendung von `class` ist **\_\_declspec \(dllexport\)** eine gute Alternative zum Erstellen von kleinerem DLLs, aber bei einer großen DLL wie MFC, ist der Standardwert, der Mechanismus exportiert, Effizienz\- und Kapazitätsgrenzen.  
  
 Dies alles bedeutet, dass wir eine große Menge an Funktionalität in Release\- MFCxx.DLL verpacken können, die nur zum 800 KB ist, ohne dabei Ausführung zu vermindern oder Geschwindigkeit zu laden.  MFCxx.DLL würde größer 100K war diese Technik nicht verwendet worden gewesen sein.  Dadurch ist es auch möglich, zusätzlichen Einstiegspunkten am Ende des .DEF hinzuzufügen aufzunehmen, um einfache Versionsverwaltung zu ermöglichen, ohne die Geschwindigkeits\- und Größeneffizienz des Exportierens zu kompromittieren nach Ordnungszahl.  Hauptversionsrevisionen in der MFC\-Klassen\-Bibliothek ändern den Bibliotheksnamen.  Das bedeutet, dass MFC30.DLL die verteilbare DLL, die Version 3.0 der MFC\-Klassen\-Bibliothek enthält.  Ein Upgrade dieser DLL sagen wir in hypothetischen MFC 3.1, die DLL MFC31.DLL würde stattdessen benannt.  Auch wenn Sie den MFC\-Quellcode ändern, um eine benutzerdefinierte Version der MFC\-DLL zu erstellen, verwenden Sie einen anderen Namen und einen \(vorzugsweise ohne "MFC" im Namen\).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)