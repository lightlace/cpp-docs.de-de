---
title: 'TN033: DLL-Version von MFC | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.dll
dev_langs: C++
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb1fb4094e5a54f82aa6aeebffe576965838cf7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: DLL-Version der MFC
Dieser Hinweis wird beschrieben, wie können Sie die MFCxx.DLL und MFCxxD.DLL (wobei x für die MFC-Versionsnummer steht) dynamic Link Librarys für MFC-Anwendungen und MFC-Erweiterungs-DLLs freigegeben. Weitere Informationen über reguläre MFC-DLLs finden Sie unter [mithilfe von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
 In diesem technischen Hinweis werden drei Aspekte der DLLs behandelt. Die letzten beiden werden für fortgeschrittene Benutzer:  
  
- [Wie Sie eine MFC-Erweiterungs-DLL erstellen](#_mfcnotes_how_to_write_an_mfc_extension_dll)  
  
- [Wie Sie eine MFC-Anwendung erstellen, die die DLL-Version von MFC verwendet.](#_mfcnotes_writing_an_application_that_uses_the_dll_version)  
  
- [Wie die MFC-Bibliothek Dynamic Link Libraries freigegeben werden implementiert.](#_mfcnotes_how_the_mfc30.dll_is_implemented)  
  
 Wenn Sie von Interesse ist, bei der Erstellung einer DLL mithilfe von MFC, die mit MFC-fremden Anwendungen verwendet werden kann (Dies ist eine reguläre MFC-DLL genannt) sind, finden Sie in [technischen Hinweis 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>Übersicht über MFCxx.DLL-Unterstützung: Terminologie und Dateien  
 **Reguläre MFC-DLL**: Verwenden Sie eine reguläre MFC-DLL, um eine eigenständige DLL mithilfe einiger der MFC-Klassen zu erstellen. Über die App-DLL-Grenze sind "C" Schnittstellen, und die Clientanwendung muss sich nicht in einer MFC-Anwendung sein.  
  
 Dies ist die Version der DLL-Unterstützung in MFC 1.0 unterstützt. Es wird beschrieben, [technischen Hinweis 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) und im MFC Advanced Concepts-Beispiel [DLLScreenCap](../visual-cpp-samples.md).  
  
> [!NOTE]
>  Ab Visual C++, Version 4.0 der Begriff **USRDLL** ist veraltet und wurde ersetzt durch eine reguläre MFC-DLL, die statisch mit MFC verknüpft. Sie können auch eine reguläre MFC-DLL erstellen, die dynamisch mit MFC verknüpft.  
  
 MFC 3.0 (und höher) unterstützt reguläre MFC-DLLs mit alle neuen Funktionen einschließlich OLE und Datenbank-Klassen.  
  
 **AFXDLL**: Dies wird auch als gemeinsam genutzte MFC-Bibliotheken Version bezeichnet. Dies ist die neue DLL-Unterstützung in MFC 2.0 hinzugefügt. Die MFC-Bibliothek selbst ist in einer Reihe von DLLs (siehe unten) und einer Clientanwendung oder die DLL dynamisch verknüpft mit die DLLs, die dies erfordert. Schnittstellen, die über die Anwendung/DLL-Grenze sind C + c++ / Schnittstellen von MFC-Klasse. Die Clientanwendung muss eine MFC-Anwendung. Unterstützt alle Funktionen von MFC 3.0 (Ausnahme: UNICODE wird nicht unterstützt, für die Datenbankklassen).  
  
> [!NOTE]
>  Ab Visual C++, Version 4.0 wird diese DLL-Typ als eine "Erweiterungs-DLL." bezeichnet.  
  
 Dieser Hinweis wird MFCxx.DLL verwenden, verweisen auf die gesamte festgelegten MFC-DLL, die enthält:  
  
-   Debug: MFCxxD.DLL (Kombination) und MFCSxxD.LIB (statisch).  
  
-   Version: MFCxx.DLL (Kombination) und MFCSxx.LIB (statisch).  
  
-   Unicode Debug: MFCxxUD.DLL (Kombination) und MFCSxxD.LIB (statisch).  
  
-   Unicode-Version: MFCxxU.DLL (Kombination) und MFCSxxU.LIB (statisch).  
  
> [!NOTE]
>  Die MFCSxx [U] [D]. LIB-Bibliotheken kommen in Verbindung mit der MFC freigegebene DLLs. Diese Bibliotheken enthalten Code, der statisch mit der Anwendung oder DLL verknüpft werden muss.  
  
 Eine Anwendung ist mit der entsprechenden Importbibliotheken verknüpft:  
  
-   Debuggen: MFCxxD.LIB  
  
-   Version: MFCxx.LIB  
  
-   Unicode Debug: MFCxxUD.LIB  
  
-   Unicode-Version: MFCxxU.LIB  
  
 Eine "MFC-Erweiterungs-DLL" ist eine DLL, die auf MFCxx.DLL basiert (und/oder die anderen freigegebenen MFC-DLLs). Hier zum Einsatz kommt der MFC-Architektur. Wenn Sie eine MFC-Klasse eine nützliche Klasse ableiten oder eine andere MFC-ähnliche Toolkit zu erstellen, können Sie es in einer DLL platzieren. DLL MFCxx.DLL, verwendet, wie die endgültigen Clientanwendung. Dies ermöglicht wiederverwendbare Leaf-Klassen, wiederverwendbare Basisklassen und wiederverwendbare Ansicht/Document-Klassen.  
  
## <a name="pros-and-cons"></a>Vor- und Nachteile  
 Warum sollten Sie gemeinsame genutzte MFC-Version verwenden  
  
-   Mithilfe der freigegebenen Bibliothek kann in kleineren Anwendungen führen (eine minimale Anwendung, die meisten der MFC-Bibliothek verwendet beträgt weniger als 10 KB).  
  
-   Gemeinsame genutzte MFC-Version unterstützt MFC-Erweiterungs-DLLs und reguläre MFC-DLLs.  
  
-   Erstellen eine Anwendung, die gemeinsam genutzte MFC-Bibliotheken verwendet, ist schneller als statisch verknüpfte MFC-Anwendung erstellen, da sie nicht zum Verknüpfen von MFC selbst benötigt wird. Dies gilt insbesondere in **DEBUGGEN** Builds, in denen der Linker die Debuginformationen komprimieren muss – durch eine Verknüpfung mit einer DLL, die bereits Debuginformationen enthält, ist es weniger Debuginformationen zu komprimieren, innerhalb der Anwendung.  
  
 Warum sollten Sie gemeinsame genutzte MFC-Version nicht verwenden:  
  
-   Verwendet eine Anwendung, die freigegebene Bibliothek verwendet, erfordert, dass Sie die MFCxx.DLL (und andere) ausgeliefert Bibliothek mit Ihrem Programm. MFCxx.DLL frei verteilt, wie viele DLLs ist allerdings weiterhin müssen die DLL im SETUP-Programm installieren können. Darüber hinaus müssen Sie die MSVCRTxx.DLL Versenden der C-Laufzeitbibliothek enthält, die vom Programm und die MFC-DLLs selbst verwendet wird.  
  
##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>Gewusst wie: Schreiben eine MFC-Erweiterungs-DLL  
 Eine MFC-Erweiterungs-DLL ist eine DLL mit Klassen und Funktionen, die die Funktionalität von der MFC-Klassen ausarbeiten geschrieben. Eine MFC-Erweiterungs-DLL verwendet die gemeinsam genutzte MFC-DLLs in die gleiche Weise wie, die eine Anwendung, die ihn Bedenken verwendet:  
  
-   Während des Erstellungsprozesses wird mit dem Erstellen einer Anwendung, die gemeinsam genutzte MFC-Bibliotheken mit ein paar zusätzliche Linkeroptionen für Compiler und verwendet, vergleichbar.  
  
-   Eine MFC-Erweiterungs-DLL verfügt nicht über eine `CWinApp`-Klasse.  
  
-   Eine MFC-Erweiterungs-DLL muss eine spezielle bieten `DllMain`. AppWizard liefert eine `DllMain` -Funktion, die Sie ändern können.  
  
-   Eine MFC-Erweiterungs-DLL wird in der Regel geben Sie eine Initialisierungsroutine zum Erstellen einer **CDynLinkLibrary** wünscht der MFC-Erweiterungs-DLL exportieren `CRuntimeClass`vorangestellten oder Ressourcen, um die Anwendung. Eine abgeleitete Klasse von **CDynLinkLibrary** kann verwendet werden, wenn durch die MFC-Erweiterungs-DLL anwendungsspezifische Daten beibehalten werden müssen.  
  
 Diese Überlegungen werden im folgenden ausführlicher beschrieben. Sie sollten auch finden Sie in der MFC Advanced Concepts-Beispiel [DLLHUSK](../visual-cpp-samples.md) seit veranschaulicht:  
  
-   Erstellen eine Anwendung mithilfe der freigegebenen Bibliotheken. (DLLHUSK. EXE-Datei ist eine MFC_Anwendung, die dynamisch mit MFC-Bibliotheken sowie andere DLLs verknüpft.)  
  
-   Erstellen eine MFC-Erweiterungs-DLL. (Beachten Sie z. B. die speziellen Flags `_AFXEXT` , die zum Erstellen einer MFC-Erweiterungs-DLL verwendet werden)  
  
-   Zwei Beispiele für MFC-Erweiterungs-DLLs. Eine zeigt die grundlegende Struktur eine MFC-Erweiterungs-DLL mit begrenzten Exporten (TESTDLL1) und das andere zeigt eine gesamte Objektklasse-Schnittstelle (TESTDLL2) exportieren.  
  
 Die Clientanwendung und alle MFC-Erweiterungs-DLLs müssen dieselbe Version von MFCxx.DLL verwenden. Sie verwenden üblicherweise MFC-DLL sollten, und geben Sie sowohl eine Debug- und retail (/ freigegeben) Version der MFC-Erweiterungs-DLL. Dies ermöglicht Clientprogramme Debug- und im Versionen ihrer Anwendungen zu erstellen und verknüpfen Sie sie mit der entsprechenden Debug- oder Verkaufsversion aller DLLs.  
  
> [!NOTE]
>  Da C++ mangling benennen und Probleme zu exportieren, kann die Exportliste einer MFC-Erweiterungs-DLL die Debug- und im Versionen derselben DLL bzw. in DLLs für unterschiedliche Plattformen unterschiedlich sein. Verkaufsversion MFCxx.DLL hat ca. 2000 Einstiegspunkte exportiert. das Debuggen MFCxxD.DLL hat ca. 3000 Einstiegspunkte exportiert.  
  
### <a name="quick-note-on-memory-management"></a>Schnelle Hinweis zur Verwaltung des Arbeitsspeichers  
 Im Abschnitt "Speicherverwaltungsfunktionen," am Ende dieser technischen Hinweis beschreibt die Implementierung der MFCxx.DLL mit der gemeinsam genutzten MFC-Version. Die Informationen müssen Sie lediglich eine MFC-Erweiterung zu implementieren, die hier DLL beschriebene kennen.  
  
 MFCxx.DLL und allen MFC-Erweiterungs-DLLs in den Adressbereich einer Clientanwendung geladen werden dieselbe Speicherbelegungsfunktion, Ladeverfahren für Ressourcen und andere "global" MFC-Zustände verwenden, als wären sie in der gleichen Anwendung. Dies ist wichtig, da die MFC - fremde DLL-Bibliotheken und reguläre MFC-DLLs, die statisch mit MFC verknüpft genau entgegengesetzt Verfahren und jede DLL belegt Speicher aus ihrem eigenen Bestand.  
  
 Eine MFC-Erweiterungs-DLL Speicher belegt wird, kann dieser Speicherbereich frei mit jedem anderen Anwendung zugeordnete Objekt mischen. Auch bei einem eine Anwendung, die gemeinsam genutzte MFC-Bibliotheken verwendet Absturz, Verwalten der Schutz des Betriebssystems die Integrität anderer MFC-Anwendung, die DLL Freigabe.  
  
 Entsprechend werden andere "global" MFC-Zustände, wie die aktuelle ausführbare Datei zum Laden von Ressourcen aus, auch von der Clientanwendung und allen MFC-Erweiterungs-DLLs sowie MFCxx.DLL selbst gemeinsam genutzt.  
  
### <a name="building-an-mfc-extension-dll"></a>Erstellen einer MFC-Erweiterungs-DLL  
 Sie können AppWizard verwenden, um ein MFC-Erweiterungs-DLL-Projekt zu erstellen, und generiert automatisch die entsprechenden Compiler und Linker-Einstellungen. Es wurde auch generieren eine `DllMain` -Funktion, die Sie ändern können.  
  
 Wenn Sie ein vorhandenes Projekt in einer MFC-Erweiterungs-DLL konvertieren, beginnen Sie mit den Standardregeln für die Erstellung einer Anwendung mit der gemeinsam genutzten MFC-Version, und führen Sie dann Folgendes:  
  
-   Hinzufügen **/D_AFXEXT** den Compiler-Flags. Wählen Sie den C-/C++-Knoten, klicken Sie im Dialogfeld "Projekteigenschaften". Wählen Sie dann die Präprozessor Kategorie. Hinzufügen `_AFXEXT` auf das Feld Definieren von Makros jedes der Elemente durch Semikolons trennen.  
  
-   Entfernen Sie die **/Gy** Compilerschalter. Wählen Sie den C-/C++-Knoten, klicken Sie im Dialogfeld "Projekteigenschaften". Wählen Sie dann die Codegenerierung-Kategorie. Stellen Sie sicher, dass die Option "Funktionslevel Linking aktivieren" nicht aktiviert ist. Dies können sie einfacher Klassen exportieren, da der Linker Unreferenzierte Funktionen nicht entfernt werden. Wenn das ursprüngliche Projekt zum Erstellen einer reguläres MFC-DLL statisch gebunden mit MFC, Änderung der **/MT [d]** -Compileroption **/MD [d]**.  
  
-   Erstellen Sie eine Exportbibliothek mit der **/DLL** Option an LINK. Dies wird festgelegt, wenn Sie ein neues Ziel erstellen Win32-Dynamic Link Library als des Zieltyps angeben.  
  
### <a name="changing-your-header-files"></a>Ändern der Headerdateien  
 Das Ziel einer MFC-Erweiterungs-DLL ist in der Regel einige allgemeine Funktionen für eine oder mehrere Anwendungen zu exportieren, die diese Funktion verwenden können. Dies führt zum Exportieren von Klassen und globale Funktionen, die für Clientanwendungen verfügbar sind.  
  
 Zu diesem Zweck müssen Sie sicherzustellen, dass jede der Memberfunktionen als importieren oder Exportieren von entsprechend markiert ist. Dies erfordert spezielle Deklarationen: **__declspec(dllexport)** und **von "__declspec(dllimport)" "**. Wenn Ihre Klassen von Clientanwendungen verwendet werden, sollen diese als deklariert werden **von "__declspec(dllimport)" "**. Wenn die MFC-Erweiterungs-DLL selbst erstellt wird, sollten sie als deklariert **__declspec(dllexport)**. Darüber hinaus müssen die Funktionen tatsächlich exportiert werden, damit sie Clientprogramme zur Ladezeit binden.  
  
 Verwenden Sie zum Exportieren der gesamten Klasse **AFX_EXT_CLASS** in der Klassendefinition. Dieses Makro wird definiert durch das Framework als **__declspec(dllexport)** Wenn **_AFXDLL** und `_AFXEXT` wird definiert, jedoch als definiert **von "__declspec(dllimport)" "** beim `_AFXEXT` ist nicht definiert. `_AFXEXT`wie oben beschrieben, wird nur definiert, wenn Sie die MFC-Erweiterungs-DLL zu erstellen. Zum Beispiel:  
  
```  
class AFX_EXT_CLASS CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
### <a name="not-exporting-the-entire-class"></a>Nicht exportieren die gesamte Klasse  
 Möglicherweise möchten nur die einzelnen erforderlichen Member einer Klasse exportieren. Angenommen, Sie exportieren eine `CDialog`-abgeleitete Klasse, müssen Sie möglicherweise nur den Konstruktor zu exportieren und die `DoModal` aufrufen. Sie können diese Elemente mithilfe der DLL exportieren. DEF-Datei, aber Sie können auch **AFX_EXT_CLASS** im großen und ganzen genauso auf die einzelnen Mitglieder, die exportiert werden müssen.  
  
 Zum Beispiel:  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
    AFX_EXT_CLASS CExampleDialog();
AFX_EXT_CLASS int DoModal();
*// rest of class definition  
 .  
 .  
 .  
};  
```  
  
 Wenn Sie dies tun, können Sie ein zusätzliches Problem ausführen, da Sie nicht mehr alle Member der Klasse exportieren. Das Problem ist auf die Weise, MFC-Makros funktionieren. Einige der MFC Hilfsmakros tatsächlich deklarieren oder Datenmember zu definieren. Daher müssen diese Datenmember auch aus einer DLL exportiert werden.  
  
 Z. B. die `DECLARE_DYNAMIC` Makro wird wie folgt definiert, wenn Sie eine MFC-Erweiterungs-DLL zu erstellen:  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
    static CRuntimeClass* PASCAL _GetBaseClass();

\  
    public: \  
    static AFX_DATA CRuntimeClass class##class_name; \  
    virtual CRuntimeClass* GetRuntimeClass() const;

\  
```  
  
 Die Zeile, beginnt "statische `AFX_DATA`" ist kein statisches Objekt innerhalb der Klasse deklarieren. Diese Klasse richtig zu exportieren und Zugriff auf die Common Language Runtime-Informationen von einem Client. EXE-Datei, müssen Sie diese statische Objekt exportieren. Da die statische Objekt mit dem Modifizierer deklariert wird `AFX_DATA`, müssen Sie nur definieren `AFX_DATA` werden **__declspec(dllexport)** beim Erstellen der DLL und definieren ihn als **von "__declspec(dllimport)" "** beim Erstellen der ausführbare Client.  
  
 Wie weiter oben erläutert **AFX_EXT_CLASS** ist bereits auf diese Weise definiert. Sie müssen nur noch neu definieren `AFX_DATA` identisch sein **AFX_EXT_CLASS** Klassendefinition.  
  
 Zum Beispiel:  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
class CExampleView : public CView  
{  
    DECLARE_DYNAMIC() *// ... class definition ...  
};  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 MFC verwendet stets die `AFX_DATA` Symbol für Datenelemente, die innerhalb der Makros definiert, sodass dieses Verfahren für alle derartigen Szenarien ausgeführt wird. Beispielsweise funktioniert er für `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Wenn Sie anstelle von ausgewählten Member der Klasse die gesamte Klasse exportieren, werden statische Datenmember automatisch exportiert.  
  
 Sie können das gleiche Verfahren verwenden, so exportieren Sie automatisch die `CArchive` Extraktionsoperator für Klassen verwendet werden, die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros. Exportieren Sie das Archiv-Operator, indem Einklammern Klassendeklarationen (befindet sich in der. H-Datei) mit den folgenden Code:  
  
```  
#undef AFX_API  
#define AFX_API AFX_EXT_CLASS  
 
<your class declarations here>  
 
#undef AFX_API  
#define AFX_API  
```  
  
### <a name="limitations-of-afxext"></a>Einschränkungen von _AFXEXT  
 Sie können die _**AFXEXT** vor Prozessor-Symbol für die MFC-Erweiterungs-DLLs, solange Sie nicht mehrere Ebenen von MFC-Erweiterungs-DLLs haben. Bei MFC-Erweiterungs-DLLs, die aufrufen oder eine Ableitung von Klassen in Ihrem eigenen MFC-Erweiterungs-DLLs, die dann von MFC-Klassen abgeleitet werden, müssen Sie eigene Präprozessorsymbol verwenden, um Mehrdeutigkeiten zu vermeiden.  
  
 Das Problem besteht darin, in Win32, müssen Sie alle Daten als explizit deklarieren **__declspec(dllexport)** wird jedoch aus einer DLL exportiert werden sollen und **von "__declspec(dllimport)" "** wird jedoch aus einer DLL importiert werden. Wenn Sie definieren `_AFXEXT`, die MFC-Header verwenden, stellen sicher, dass **AFX_EXT_CLASS** ordnungsgemäß definiert ist.  
  
 Wenn Sie haben mehrere Ebenen, ein Symbol wie z. B. **AFX_EXT_CLASS** ist nicht ausreichend, da eine MFC-Erweiterungs-DLL kann werden neue Klassen exportieren als auch andere Klassen von einem anderen MFC-Erweiterungs-DLL importieren. Um dieses Problem zu beheben, verwenden Sie ein spezielles Präprozessorsymbol, das angibt, dass Sie die DLL im Vergleich zum Verwenden der DLL erstellen. Nehmen Sie z. B., MFC-Erweiterungs-DLLs, A.DLL und B.DLL. Jeder exportieren bzw. einige Klassen in A.H bzw. B.H. B.DLL verwendet die Klassen von A.DLL. Die Headerdateien würde etwa wie folgt aussehen:  
  
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
  
 Wenn a.dll wird er basiert **/d A_IMPL** und wenn B.DLL erstellt wird, wird es anhand erstellt **/d B_IMPL**. Getrennte Symbole für jede DLL-Datei verwenden, CExampleB exportiert, und beim Erstellen von B.DLL CExampleA importiert. CExampleA wird beim Erstellen von A.DLL exportiert und importiert, wenn von B.DLL (oder einem anderen Client) verwendet.  
  
 Diese Art der Schichtung kann nicht durchgeführt werden, bei Verwendung die integrierten **AFX_EXT_CLASS** und `_AFXEXT` Präprozessorsymbole. Die oben beschriebene Technik löst dieses Problem in einer Weise, die nicht im Gegensatz zum, die Mechanismus MFC selbst verwendet werden soll, wenn der OLE-Datenbank und Netzwerk MFC-Erweiterungs-DLLs zu erstellen.  
  
### <a name="not-exporting-the-entire-class"></a>Nicht exportieren die gesamte Klasse  
 In diesem Fall müssen Sie besondere Sorgfalt vorgehen, wenn Sie eine gesamte Objektklasse nicht exportiert werden. Sie müssen sicherstellen, dass die erforderlichen Datenelemente, die von der MFC-Makros erstellt ordnungsgemäß exportiert werden. Dies kann geschehen, indem Sie neu definieren **AFX_DATA** Makro für Ihre spezifische Klasse. Diese Einstellung sollte jedes Mal vorgenommen werden Sie nicht die gesamte Klasse exportieren.  
  
 Zum Beispiel:  
  
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
*//class definition   
 .  
 .  
 .  
};  
 
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### <a name="dllmain"></a>DllMain  
 Im folgenden wird der genaue Code, den Sie in der main-Quelldatei für die MFC-Erweiterungs-DLL ablegen soll. Es sollte eingesetzt werden, nachdem die-Standard umfasst. Beachten Sie, dass wenn Sie mithilfe von AppWizard um Ausgangsdateien für eine MFC-Erweiterungs-DLL zu erstellen, stellt eine `DllMain` für Sie.  
  
```  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE extensionDLL;  
  
extern "C" int APIENTRY   
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      // MFC extension DLL one-time initialization   
      if (!AfxInitExtensionModule(  
             extensionDLL, hInstance))  
         return 0;  
  
      // TODO: perform other initialization tasks here  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      // MFC extension DLL per-process termination  
      AfxTermExtensionModule(extensionDLL);  
  
          // TODO: perform other cleanup tasks here  
   }  
   return 1;   // ok  
}  
```  
  
 Der Aufruf von `AfxInitExtensionModule` Laufzeitklassen Module erfasst (`CRuntimeClass` Strukturen) sowie die Objektfactory (`COleObjectFactory` Objekte) für die Verwendung höher bei der **CDynLinkLibrary** Objekt erstellt wird. (Optional) Aufruf `AfxTermExtensionModule` können MFC Cleanup der MFC-Erweiterungs-DLL beim trennt jeder Prozess (das geschieht, wenn der Prozess beendet wird oder wenn die DLL entladen wird, als Ergebnis des eine **FreeLibrary** aufrufen) von den MFC-Erweiterungs-DLL . Da die meisten MFC-Erweiterungs-DLLs nicht dynamisch geladen werden werden (in der Regel verknüpft sind über ihre Importbibliotheken), den Aufruf von `AfxTermExtensionModule` ist in der Regel nicht erforderlich.  
  
 Wenn die Anwendung lädt und MFC-Erweiterungs-DLLs dynamisch freigegeben, achten Sie darauf Aufrufen `AfxTermExtensionModule` wie oben gezeigt. Achten Sie auch darauf verwenden `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle von Win32-Funktionen **LoadLibrary** und **FreeLibrary**), wenn Ihre Anwendung mehrere Threads verwendet oder einen dynamisch geladen Erweiterungs-DLL. Mit `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass das Starten und Herunterfahren Code, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL geladen und entladen wird, die nicht über den Status der globalen MFC beschädigt.  
  
 Die Headerdatei AFXDLLX. H enthält spezielle Definitionen für Strukturen verwendet, die in MFC-Erweiterungs-DLLs, z. B. die Definition für `AFX_EXTENSION_MODULE` und **CDynLinkLibrary**.  
  
 Die globale *ExtensionDLL* muss deklariert werden, wie gezeigt. Im Gegensatz zu den 16-Bit-Version von MFC können Sie Speicher und MFC-Funktionen in diesem Zeitraum aufgerufen werden, da die MFCxx.DLL Zeitpunkt vollständig initialisiert wurde Ihr `DllMain` aufgerufen wird.  
  
### <a name="sharing-resources-and-classes"></a>Gemeinsame Nutzung von Ressourcen und Klassen  
 Einfache MFC-Erweiterungs-DLLs müssen nur wenige mit geringer Bandbreite-Funktionen in der Clientanwendung und nichts mehr exportieren. Weitere Benutzeroberfläche rechenintensiven-DLLs sollten Ressourcen und C++-Klassen in der Clientanwendung zu exportieren.  
  
 Der Export von Ressourcen erfolgt über eine Ressourcenliste. Jede Anwendung ist eine einfach verknüpfte Liste mit **CDynLinkLibrary** Objekte. Bei der Suche nach einer Ressource, für die meisten MFC-standardimplementierungen, die Ressourcen geladen werden zunächst im aktuellen Ressourcenmodul suchen (`AfxGetResourceHandle`) und Walk wurde nicht gefunden, wenn die Liste der **CDynLinkLibrary** Objekte, die beim Laden der angeforderte Ressource.  
  
 Die dynamische Erstellung von C++-Objekten, die anhand einer C++-Klassenname gleicht. Der Mechanismus zur Deserialisierung von MFC-Objekt, dass alle muss die `CRuntimeClass` Objekte registriert Weise Informationen mittels dynamischer Erstellung C++-Objekt des erforderlichen Typs anhand der zuvor gespeicherten rekonstruiert werden kann.  
  
 Wenn Sie möchten, dass die Clientanwendung Klassen in der MFC-Erweiterungs-DLL zu verwenden, sind `DECLARE_SERIAL`, müssen Sie die Klassen aus, um für die Client-Anwendung sichtbar zu exportieren. Dies erfolgt auch durch das Durchlaufen der **CDynLinkLibrary** Liste.  
  
 Im Fall von im MFC Advanced Concepts-Beispiel [DLLHUSK](../visual-cpp-samples.md), die Liste sieht ungefähr so aus:  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
 |      |  
    TESTDLL2.DLL TESTDLL2.DLL  
 |      |  
    TESTDLL1.DLL TESTDLL1.DLL  
 |      |  
 |      |  
    MFC90D.DLL MFC90.DLL  
```  
  
 Die MFCxx.DLL ist in der Ressourcen- und Klassenliste gewöhnlich letzte. MFCxx.DLL umfasst alle einschließlich der eingabeaufforderungen aller Standardbefehls-IDs für MFC-Standardressourcen. Legen Sie das Element am Ende der Liste kann DLLs und die Clientanwendung selbst keine eigene Kopie des MFC-Standardressourcen, aber auf basieren auf freigegebenen Ressourcen in MFCxx.DLL stattdessen.  
  
 Zusammenführen von Ressourcen und Klassennamen aller DLLs in der Clientanwendung Namespace hat den Nachteil, die Sie darauf achten, dass was IDs oder Namen, die Sie auswählen. Sie können natürlich Deaktivieren dieser Funktion durch den Export nicht entweder Ihre Ressourcen oder eine **CDynLinkLibrary** Objekt an die Clientanwendung. Die [DLLHUSK](../visual-cpp-samples.md) Beispiel Namespace freigegebene Ressource mithilfe mehrerer Headerdateien verwaltet. Finden Sie unter [technischen Hinweis 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) Weitere Tipps zur Verwendung der gemeinsam genutzte Ressourcendateien.  
  
### <a name="initializing-the-dll"></a>Initialisieren der DLL  
 Wie bereits erwähnt, sollten Sie in der Regel erstellen Sie eine **CDynLinkLibrary** Objekt, um Ihre Ressourcen und Klassen an die Clientanwendung zu exportieren. Sie benötigen, geben Sie einen exportierte Einstiegspunkt für die DLL jedoch initialisiert werden. Minimal, dies ist eine "void" Routine, die keine Argumente akzeptiert und gibt nichts zurück, jedoch kann alles gewünschte sein.  
  
 Wenn Sie diesen Ansatz verwenden, muss jede Clientanwendung, die die DLL verwenden möchte diese Initialisierungsroutine aufrufen. Kann auch dadurch reservieren **CDynLinkLibrary** Objekt in Ihrem `DllMain` nur nach dem Aufruf `AfxInitExtensionModule`.  
  
 Erstellen Sie die Initialisierungsroutine muss eine **CDynLinkLibrary** Objekt in der aktuellen Anwendung Heap angeschlossen an die MFC-Erweiterungs-DLL-Informationen. Dies kann wie folgt erfolgen:  
  
```  
extern "C" extern void WINAPI InitXxxDLL()  
{  
    new CDynLinkLibrary(extensionDLL);

}  
```  
  
 Die Namen der Routine *InitXxxDLL* in diesem Beispiel kann beliebig sein. Er muss nicht werden `extern "C"`, aber auf diese Weise ermöglicht die Exportliste einfacher zu verwalten.  
  
> [!NOTE]
>  Wenn Sie die MFC-Erweiterungs-DLL über reguläre MFC-DLL verwenden, müssen Sie diese Initialisierungsfunktion exportieren. Diese Funktion muss zu den regulären MFC-DLL aufgerufen werden, bevor Sie mit einem beliebigen MFC-DLL Erweiterungsklassen oder Ressourcen.  
  
### <a name="exporting-entries"></a>Exportieren von Einträgen  
 Die einfache Möglichkeit zum Exportieren von Klassen ist die Verwendung **von "__declspec(dllimport)" "** und **__declspec(dllexport)** für jede Klasse und die globale Funktion, die Sie exportieren möchten. Dies macht es viel einfacher, aber es ist weniger effizient als jeden Einstiegspunkt (unten beschrieben) die Benennung, da haben Sie weniger Kontrolle über welche Funktionen exportiert werden, und Sie können nicht die Funktionen anhand der Ordinalzahl exportieren. TESTDLL1 und TESTDLL2 verwenden Sie diese Methode, die Servereinträge exportieren.  
  
 Eine effizientere Methode (und die Methode von MFCxx.DLL verwendet) werden jeder Eintrag Exportieren per hand katalogisiert wird durch jeden Eintrag in der Benennung der. DEF-Datei. Da wir aus unserer DLL (d. h. nicht alles) selektiven Exporte exportieren, müssen wir entscheiden, welche bestimmten Schnittstellen wir exportieren möchten. Dies ist schwierig, da Sie die ergänzten Namen an den Linker, in Form von Einträgen in angeben müssen der. DEF-Datei. Alle C++-Klassen nicht exportiert werden, es sei denn, Sie tatsächlich benötigen eine symbolische Verknüpfung dafür.  
  
 Wenn Sie versucht haben, Exportieren von C++ Klassen mit ein. DEF-Datei, bevor Sie ein Tool zum Generieren von automatisch dieser Liste entwickeln möchten. Dies kann erfolgen über einen Link von einem zweistufigen Prozess. Verknüpfen Sie die DLL einmal mit keine Exporte und ermöglichen den Linker an generieren ein. MAP-Datei. Die. Zuordnungsdatei kann verwendet werden, um eine Liste der Funktionen, die exportiert werden soll, zu generieren, damit mit einigen neu anordnen, es verwendet werden kann, generieren die EXPORT-Einträge für Ihre. DEF-Datei. (Obwohl es nicht vollständig automatisierten und erfordert einige Hand einmal in eine Weile optimieren), wurde die Exportliste für MFCxx.DLL OLE und die Datenbank-MFC-Erweiterungs-DLLs, mehrere Tausend bezüglich Anzahl, mit solchen Prozess generiert.  
  
### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp-im Vergleich zu CDynLinkLibrary  
 Eine MFC-Erweiterungs-DLL verfügt nicht über eine `CWinApp`-abgeleitetes Objekt selbst; stattdessen müssen sie gemeinsam mit der `CWinApp`-abgeleitetes Objekt der Clientanwendung. Dies bedeutet, dass die Clientanwendung die Haupt-Meldungsverteilschleife, die Leerlaufschleife usw. besitzt.  
  
 Wenn die MFC-Erweiterungs-DLL spezielle Daten für jede Anwendung verwalten muss, leiten Sie eine neue Klasse von **CDynLinkLibrary** und erstellen Sie ihn in die InitXxxDLL Routine oben beschrieben. Beim Ausführen, kann die DLL Überprüfen der aktuellen Anwendung Liste **CDynLinkLibrary** -Objekten, die das Objekt für die jeweilige MFC-Erweiterungs-DLL zu suchen.  
  
### <a name="using-resources-in-your-dll-implementation"></a>Verwenden von Ressourcen in der DLL-Implementierung  
 Wie bereits erwähnt, führt die standardmäßige ressourcenauslastung die Liste der **CDynLinkLibrary** Objekte, die Suche nach der ersten exe- oder DLL, die die angeforderte Ressource verfügt. Alle MFC-APIs sowie alle der internen Code verwendet `AfxFindResourceHandle` , durchlaufen die Ressourcenliste um jede Ressource wird, unabhängig davon, wo es befinden sich möglicherweise zu suchen.  
  
 Wenn Sie nur Ressourcen von einer bestimmten Stelle laden möchten, verwenden Sie die APIs `AfxGetResourceHandle` und `AfxSetResourceHandle` das alte Handle zu speichern und das neue Handle festzulegen. Achten Sie darauf, dass Sie das alte Ressourcenhandle wiederherstellen, bevor Sie zur Clientanwendung zurückkehren. Im Beispiel TESTDLL2 wird dieser Ansatz zum Laden von explizit ein Menü verwendet.  
  
 Das Durchlaufen der Liste hat jedoch den Nachteil, dass die Suche etwas langsamer ist und dass die Ressourcen-ID-Bereiche verwaltet werden müssen. Es hat den Vorteil, dass eine Clientanwendung, die mit mehreren MFC-Erweiterungs-DLLs verknüpft jede DLL bereitgestellten Ressource verwenden kann, ohne die DLL-Instanzenhandle angegeben. `AfxFindResourceHandle` ist eine API, die bei der Suche nach einer bestimmten Übereinstimmung die Ressourcenliste durchläuft. Sie verwendet den Ressourcennamen und -typ als Parameter und gibt das zuerst ermittelte Ressourcenhandle (oder NULL) zurück.  
  
##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>Schreiben einer Anwendung, die die DLL-Version verwendet.  
  
### <a name="application-requirements"></a>Anwendungsanforderungen  
 Eine Anwendung, die gemeinsam genutzte MFC-Version verwendet, muss einige einfache Regeln ausführen:  
  
-   Sie benötigen ein `CWinApp` Objekt, und befolgen Sie die Standardregeln für die ein Nachrichtensystem.  
  
-   Sie müssen mit einem Satz von erforderlichen Compilerflags (siehe unten) kompiliert werden.  
  
-   Es muss mit der MFCxx Importbibliotheken verknüpft werden. Durch Festlegen der erforderlichen Compilerflags, bestimmen Sie die MFC-Header zum Zeitpunkt der Verknüpfung die Bibliothek, die die Anwendung mit verknüpft werden soll.  
  
-   Führen Sie die ausführbare Datei muss MFCxx.DLL auf den Pfad oder im Windows-Systemverzeichnis.  
  
### <a name="building-with-the-development-environment"></a>Erstellen mit der Entwicklungsumgebung  
 Bei Verwendung von internen Makefile mit einem Großteil der Standardwerte können Sie einfach das Projekt zum Erstellen der DLL-Version ändern.  
  
 Im folgenden Schritt wird davon ausgegangen, dass Sie eine ordnungsgemäß funktionierende MFC_Anwendung mit NAFXCWD verknüpft haben. LIB (für Debug) und NAFXCW. LIB (für den Einzelhandel) und Sie möchten konvertieren, um die freigegebene Version der MFC-Bibliothek verwenden. Sie die Visual C++-Umgebung ausgeführt werden und eine interne Projektdatei an.  
  
1.  Auf der **Projekte** Menü klicken Sie auf **Eigenschaften**. In der **allgemeine** Seite **Projektstandards**, legen Sie die Microsoft Foundation Classes auf **MFC in einer gemeinsam genutzten DLL verwenden** (MFCxx(d).dll).  
  
### <a name="building-with-nmake"></a>Beim Erstellen mit NMAKE  
 Wenn Sie die externes Makefile-Funktion von Visual C++ verwenden oder direkt NMAKE verwenden, müssen Sie die Makefile zur Unterstützung von Compiler- und Linkeroptionen bearbeiten  
  
 Compilerflags erforderlich:  
  
 **/ D_AFXDLL/MD**  
 **/ D_AFXDLL**  
  
 MFC-Standardheader benötigen dieses Symbol definiert werden:  
  
 **/MD**  
 Die Anwendung muss die DLL-Version der C-Laufzeitbibliothek verwenden.  
  
 Alle anderen Compilerflags führen Sie die MFC-Standardeinstellungen (z. B. _DEBUG für Debug).  
  
 Bearbeiten Sie die Linker-Liste der Bibliotheken. NAFXCWD ändern. LIB-MFCxxD.LIB, und ändern Sie NAFXCW. LIB, MFCxx.LIB. Ersetzen Sie LIBC. LIB mit MSVCRT. LIB. Wie mit anderen MFC-Bibliothek es wichtig ist, dass MFCxxD.LIB platziert wird **vor** alle C-Laufzeitbibliotheken.  
  
 Fügen Sie optional **/D_AFXDLL** für Ihre Verkaufsversionen und Resource-Compileroptionen (derjenige, der die Ressourcen mit tatsächlich kompiliert **/r**). Dadurch erhält die endgültige ausführbare kleinere durch die Freigabe der Ressourcen, die in der MFC-DLLs vorhanden sind.  
  
 Eine vollständige Neuerstellung ist erforderlich, nachdem diese Änderungen vorgenommen wurden.  
  
### <a name="building-the-samples"></a>Erstellen der Beispiele  
 Die meisten MFC-Beispielprogramme können von Visual C++ oder mit einem freigegebenen NMAKE-kompatiblen MAKEFILE über die Befehlszeile erstellt werden.  
  
 Um diese Beispiele verwenden MFCxx.DLL zu konvertieren, laden Sie die. MAK-Datei in Visual C++-Komponente und das Projekt festzulegen, wie oben beschrieben. Wenn Sie den NMAKE-Build verwenden, können Sie angeben "AFXDLL = 1" auf der NMAKE einer Befehlszeile und, wird im Beispiel mit der gemeinsam genutzten MFC-Bibliotheken erstellen.  
  
 Im MFC Advanced Concepts-Beispiel [DLLHUSK](../visual-cpp-samples.md) mit der DLL-Version von MFC erstellt wurde. Dieses Beispiel veranschaulicht das nicht nur zum Erstellen einer Anwendung mit MFCxx.DLL verknüpft, aber es zeigt darüber hinaus andere Funktionen von der MFC-DLL Packaging-Option wie z. B. MFC-Erweiterungs-DLLs, die weiter unten in diesem technischen Hinweis beschrieben.  
  
### <a name="packaging-notes"></a>Verpacken Hinweise  
 Die Verkaufsversion von DLLs (MFCxx [U]. (DLL) können frei verteilt. Die Debugversion der DLLs sind nicht frei verteilt und sollte nur während der Entwicklung der Anwendung verwendet werden.  
  
 Das Debuggen von DLLs mit Debuginformationen zur Verfügung. Mithilfe von Visual C++-Debugger können Sie die Ausführung Ihrer Anwendung sowie die DLL verfolgen. Die Release-DLLs (MFCxx [U]. (DLL) werden keine Debuginformationen.  
  
 Wenn Sie anpassen oder erstellen Sie die DLLs neu, sollten Sie sie ein Element als "MFCxx" der MFC-SRC-Datei MFCDLL aufrufen. MAK Buildoptionen beschreibt und enthält die Logik für die DLL umbenennen. Umbenennen von Dateien ist notwendig, da diese DLLs potenziell von vielen MFC-Anwendungen gemeinsam verwendet werden. Mit der benutzerdefinierten Version von MFC-DLLs ersetzen können diese auf dem System installiert eine andere MFC-Anwendung, die mit der gemeinsam genutzten MFC-DLLs umbrochen werden.  
  
 Das Neuerstellen der MFC-DLLs wird nicht empfohlen.  
  
##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>Wie wird die MFCxx.DLL implementiert.  
 Im folgenden Abschnitt wird beschrieben, wie die MFC-DLL (MFCxx.DLL und MFCxxD.DLL) implementiert wird. Grundlegendes zu, dass die entsprechenden Informationen hier auch nicht ist wichtig, wenn alle Sie möchten die MFC-DLL mit der Anwendung verwendet. Die entsprechenden Informationen hier sind nicht wichtig, um zu verstehen, wie Sie eine MFC-Erweiterungs-DLL zu schreiben, aber Grundlegendes zu dieser Implementierung, können Sie Ihre eigene DLL zu schreiben.  
  
### <a name="implementation-overview"></a>Übersicht über die Implementierung  
 Die MFC-DLL ist tatsächlich ein Sonderfall des eine MFC-Erweiterungs-DLL, wie oben beschrieben. Es wurde eine sehr große Anzahl von Exporten für eine große Anzahl von Klassen. Es sind einige zusätzliche Aufgaben ausführen wir in der MFC-DLL, die es sogar noch stärker als eine reguläre MFC-Erweiterungs-DLL spezielle machen.  
  
### <a name="win32-does-most-of-the-work"></a>Win32 übernimmt den Großteil der Arbeit  
 Die 16-Bit-Version von MFC benötigt eine Reihe von speziellen Techniken einschließlich pro app-Daten im Segment Stapel spezielle Segmente erstellt, indem einige 80 x 86-Assemblycode, pro Prozess Ausnahme Kontexte und andere Techniken. Win32 unterstützt direkt prozessspezifisch Daten in eine DLL ist in den meisten Fällen erwünscht. Meistens ist MFCxx.DLL nur NAFXCW. LIB, die in einer DLL zusammengefasst. Bei Betrachtung des Quellcodes MFC finden Sie nur sehr wenige #ifdef _AFXDLL, da es sich um sehr wenige spezielle Fälle, die vorgenommen werden müssen. Die besondere Fälle, es gibt insbesondere für den Umgang mit Win32 auf Windows 3.1 (auch bekannt als Win32s). Win32s ist keine Unterstützung prozessspezifisch DLL Daten direkt daher die MFC-DLL für den lokalen Threadspeicher (TLS) Win32-APIs zum Verarbeiten von lokalen Daten abrufen verwenden, müssen.  
  
### <a name="impact-on-library-sources-additional-files"></a>Auswirkungen auf die Bibliothekquellen, zusätzliche Dateien  
 Die Auswirkungen der **_AFXDLL** -Version auf die normale MFC-Klasse Bibliothekquellen und Header ist relativ geringfügiges. Es ist eine spezielle Version-Datei (AFXV_DLL. H) sowie eine zusätzliche Headerdatei (AFXDLL_. H) in die wichtigsten AFXWIN enthalten. H-Header. Die AFXDLL_. H-Header enthält das **CDynLinkLibrary** Klasse und weitere Implementierungsdetails beider **_AFXDLL** Anwendungen und MFC-Erweiterungs-DLLs. Die AFXDLLX. H-Header wird zum Erstellen von MFC-Erweiterungs-DLLs (siehe oben) bereitgestellt.  
  
 Die regulären Quellen der MFC-Bibliothek in MFC SRC weisen einige zusätzlichen bedingten Code unter der **_AFXDLL** #ifdef. Eine zusätzliche Quelldatei (DLLINIT. CPP) enthält die zusätzlichen Initialisierungscode einer DLL und andere Kleben für gemeinsam genutzte MFC-Version.  
  
 Um die gemeinsam genutzte MFC-Version zu erstellen, werden zusätzliche Dateien bereitgestellt. (Siehe unten für Informationen zu den DLL-Datei erstellen.)  
  
-   Zwei. DEF-Dateien dienen zum Exportieren der MFC-DLL-Einstiegspunkte für Debug (MFCxxD.DEF) und Releaseversionen (MFCxx.DEF) der DLL.  
  
-   Ein. RC-Datei (MFCDLL. RC) enthält alle MFC-Standardressourcen und VERSIONINFO-Ressource, für die DLL.  
  
-   EIN. CLW-Datei (MFCDLL. CLW) wird ermöglicht, durchsuchen die MFC-Klassen mit ClassWizard bereitgestellt. Hinweis: Diese Funktion ist nicht speziell für die DLL-Version von MFC.  
  
### <a name="memory-management"></a>Speicherverwaltung  
 Eine Anwendung mit MFCxx.DLL verwendet eine allgemeine speicherbelegung von MSVCRTxx.DLL, der gemeinsam genutzten DLL der C-Laufzeit bereitgestellt. Die Anwendung, alle MFC-Erweiterungs-DLLs und sowie die MFC-DLLs selbst verwenden diese freigegebenen Speicherbelegungsfunktion. Mithilfe einer gemeinsam genutzten DLL für die speicherbelegung kann die MFC-DLLs belegt werden, die später von der Anwendung oder umgekehrt freigegeben wird. Da die Anwendung und die DLL die gleiche Zuweisung verwendet werden muss, sollten Sie nicht die globale C++ überschreiben `operator new` oder `operator delete`. Die gleichen Regeln gelten für die restliche der C-Laufzeitspeicher-Reservierungsroutinen (z. B. `malloc`, `realloc`, **freien**, usw.).  
  
### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>Ordinalzahlen und Klasse __declspec(dllexport) und DLL-Namen  
 Wir verwenden die `class` **__declspec(dllexport)** Funktionalität des C++-Compilers. Stattdessen wird eine Reihe von Exporten in die Klasse Bibliothekquellen (MFCxx.DEF und MFCxxD.DEF) enthalten. Nur diese ausgewählten Satz von Einstiegspunkte (Funktionen und Daten) werden exportiert. Anderen Symbolen, z. B. private Implementierung von MFC-Funktionen oder Klassen werden nicht exportiert alle Exporte nach Ordnungszahl namenlose Zeichenfolge in der Namenstabelle residenten oder nicht Resident fertig sind.  
  
 Mit `class` **__declspec(dllexport)** möglicherweise eine gute Alternative zum Erstellen von kleineren DLLs, aber bei einer großen DLL wie MFC, die Standardeinstellung exportieren Mechanismus hat, Effizienz und Kapazität Grenzwerte.  
  
 Demnach alle Neuigkeiten, dass wir eine große Menge an Funktionalität in der Version MFCxx.DLL Verpacken können, die nur ca. 800 KB ohne viel Ausführung gefährden oder laden die Geschwindigkeit ist. MFCxx.DLL hätte 100K größer diese Technik nicht wurde verwendet. Auch dadurch möglich, Hinzufügen von zusätzlichen Einstiegspunkte am Ende der. DEF-Datei, um einfache versionsverwaltung zu ermöglichen, ohne Beeinträchtigung der Geschwindigkeit und Größe Effizienz durch die Ordinalzahl zu exportieren. Hauptversion Revisionen in der MFC-Klassenbibliothek ändert sich der Bibliotheksname. D. h. MFC30. DLL ist die redistributable-DLL, Version 3.0 der MFC-Klassenbibliothek enthält. Ein Upgrade dieser DLL z. B. in einer hypothetischen 3.1 MFC-DLL MFC31 benannt werden würde. DLL stattdessen. Erneut, wenn Sie die MFC-Quellcode um eine benutzerdefinierte Version der MFC-DLL zu erzeugen ändern, verwenden Sie einen anderen Namen (und bevorzugt ohne "MFC" im Namen).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

