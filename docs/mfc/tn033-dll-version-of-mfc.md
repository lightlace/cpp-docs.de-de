---
title: 'TN033: DLL-Version der MFC'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.dll
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
ms.openlocfilehash: 17ffc8b46060e742449c9612424b1cd06dd8a9d3
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523961"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: DLL-Version der MFC

In diesem Hinweis wird beschrieben, wie können Sie die MFCxx.DLL und MFCxxD.DLL (wobei x für die MFC-Versionsnummer ist), dynamic Link Librarys für MFC-Anwendungen und MFC-Erweiterungs-DLLs zu freigegeben. Weitere Informationen zu regulären MFC-DLLs, finden Sie unter [mithilfe von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

Diese technische Hinweis umfasst drei Aspekte der DLLs. Die letzten beiden sind für fortgeschrittene Benutzer:

- [Wie Sie eine MFC-Erweiterungs-DLL erstellen](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [Wie Sie eine MFC-Anwendung erstellen, die die DLL-Version von MFC verwendet.](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [Wie die MFC-Dynamic Link Libraries freigegeben werden implementiert.](#_mfcnotes_how_the_mfc30.dll_is_implemented)

Wenn Sie bei der Erstellung einer DLL mithilfe von MFC, die mit MFC-fremden Anwendungen verwendet werden kann (Dies ist eine reguläre MFC-DLL bezeichnet), finden Sie unter [technischen Hinweis 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>Übersicht über die MFCxx.DLL-Unterstützung: Terminologie und Dateien

**Reguläre MFC-DLL**: Verwenden Sie eine reguläre MFC-DLL an, um eine eigenständige DLL mithilfe einiger der MFC-Klassen zu erstellen. Über die App/DLL-Grenze hinweg sind "C"-Schnittstellen, und die Client-Anwendung muss keiner MFC-Anwendung sein.

Dies ist die Version der DLL-Unterstützung in MFC 1.0 unterstützt. Es wird beschrieben, [technischen Hinweis 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) und im MFC Advanced Concepts-Beispiel [DLLScreenCap](../visual-cpp-samples.md).

> [!NOTE]
> Ab Visual C++ 4.0 ist der Begriff **USRDLL** ist veraltet und wurde ersetzt durch eine reguläre MFC-DLL, die statisch mit MFC verknüpft. Sie können auch eine reguläre MFC-DLL erstellen, die dynamisch mit MFC verknüpft wird.

MFC 3.0 (und höher) unterstützt reguläre MFC-DLLs mit allen neuen Funktionen einschließlich der Klassen OLE und der Datenbank.

**AFXDLL**: Dies wird auch als die freigegebene Version von MFC-Bibliotheken bezeichnet. Dies ist die neue DLL-Unterstützung in MFC 2.0 hinzugefügt. Die MFC-Bibliothek selbst ist in einer Reihe von DLLs (siehe unten) und einer Clientanwendung oder die DLL dynamisch verknüpft mit die DLLs, die es benötigt. Schnittstellen für die Anwendung/DLL-Grenze sind C++ / MFC-Klasse-Schnittstellen. Die Clientanwendung muss eine MFC-Anwendung. Unterstützt alle Funktionen von MFC 3.0 (Ausnahme: UNICODE wird nicht unterstützt, für die Datenbankklassen).

> [!NOTE]
> Ab Visual C++, Version 4.0 wird die DLL als ein "Erweiterungs-DLL." bezeichnet.

In diesem Hinweis wird MFCxx.DLL verwenden, verweisen auf die gesamte, MFC-DLL festgelegt, die enthält:

- Debuggen: MFCxxD.DLL (kombiniert) und MFCSxxD.LIB (statisch).

- Version: MFCxx.DLL (kombiniert) und MFCSxx.LIB (statisch).

- Unicode-Debug: MFCxxUD.DLL (kombiniert) und MFCSxxD.LIB (statisch).

- Unicode-Version: MFCxxU.DLL (kombiniert) und MFCSxxU.LIB (statisch).

> [!NOTE]
> Die MFCSxx [U] [D]. LIB-Bibliotheken werden verwendet, Verbindung mit die MFC-Bibliothek freigegebene DLLs. Diese Bibliotheken enthalten Code, der statisch mit der Anwendung oder DLL verknüpft sein muss.

Importieren Sie eine Anwendung eine Verknüpfung mit der entsprechenden Bibliotheken:

- Debuggen: MFCxxD.LIB

- Version: MFCxx.LIB

- Unicode-Debug: MFCxxUD.LIB

- Unicode-Version: MFCxxU.LIB

Eine "MFC-Erweiterungs-DLL" ist eine DLL, die MFCxx.DLL aufbaut (und/oder die anderen freigegebenen MFC-DLLs). Hier wird die MFC-Komponentenarchitektur ein. Wenn Sie eine MFC-Klasse eine nützliche Klasse ableiten oder eine andere MFC-ähnliche Toolkit zu erstellen, können Sie es in einer DLL platzieren. DLL MFCxx.DLL, verwendet, wie die ultimate-Client-Anwendung. Dies ermöglicht die wiederverwendbare untergeordneten Klassen, wiederverwendbare Basisklassen und wiederverwendbare anzeigen/Document-Klassen.

## <a name="pros-and-cons"></a>Vor- und Nachteile

Warum sollten Sie die freigegebene Version von MFC verwenden

- Verwenden die freigegebene Bibliothek kann in kleinere Anwendungen führen (eine minimale Anwendung, die meisten der MFC-Bibliothek verwendet beträgt weniger als 10 KB).

- Die freigegebene Version von MFC unterstützt die MFC-Erweiterungs-DLLs und regulären MFC-DLLs.

- Erstellen eine Anwendung, die gemeinsam genutzten MFC-Bibliotheken verwendet, ist schneller als eine statisch verknüpfte MFC-Anwendung erstellen, da es nicht erforderlich, um MFC selbst zu verknüpfen ist. Dies gilt insbesondere in **DEBUGGEN** Builds, in denen der Linker die Debuginformationen komprimieren muss – durch das Verknüpfen mit einer DLL, die bereits Debuginformationen enthält, ist es weniger Debuginformationen zu komprimieren in Ihrer Anwendung.

Warum sollten Sie die freigegebene Version von MFC nicht verwenden:

- Versenden eine Anwendung, die freigegebene Bibliothek verwendet, auszuliefern MFCxx.DLL (und andere) erfordert die Bibliothek mit Ihrem Programm. MFCxx.DLL ist kostenlos weiterverteilbar ist, wie viele DLLs, aber dennoch müssen Sie installieren die DLL in das Setupprogramm. Darüber hinaus müssen Sie die MSVCRTxx.DLL versenden die C-Laufzeitbibliothek enthält, die sowohl durch das Programm und die MFC-DLLs selbst verwendet wird.

##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> Gewusst wie: Schreiben eine MFC-Erweiterungs-DLL

Eine MFC-Erweiterungs-DLL ist eine DLL, Klassen und Funktion, um die Funktionalität von der MFC-Klassen geschenkband enthält. Eine MFC-Erweiterungs-DLL verwendet die gemeinsam genutzte MFC-DLLs, auf die gleiche Weise, die eine Anwendung, mit einigen zusätzlichen Einschränkungen verwendet:

- Der Buildprozess ist vergleichbar mit dem Erstellen einer Anwendung, die gemeinsam genutzten MFC-Bibliotheken mit ein paar zusätzliche Compiler- und Linkeroptionen verwendet.

- Eine MFC-Erweiterungs-DLL verfügt nicht über eine `CWinApp`-abgeleitete Klasse.

- Geben Sie eine MFC-Erweiterungs-DLL muss eine spezielle `DllMain`. AppWizard liefert eine `DllMain` -Funktion, die Sie ändern können.

- Eine MFC-Erweiterungs-DLL wird in der Regel geben Sie eine Initialisierungsroutine zum Erstellen einer `CDynLinkLibrary` Wenn die MFC-Erweiterungs-DLL exportieren möchte `CRuntimeClass`es oder Ressourcen, um die Anwendung. Eine abgeleitete Klasse von `CDynLinkLibrary` kann verwendet werden, wenn nach Anwendung von der MFC-Erweiterungs-DLL beibehalten werden muss.

Diese Überlegungen werden im folgenden ausführlicher beschrieben. Lesen Sie auch im MFC Advanced Concepts-Beispiel [DLLHUSK](../visual-cpp-samples.md) , da das Beispiel veranschaulicht:

- Erstellen eine Anwendung, die gemeinsam genutzten Bibliotheken. (DLLHUSK. EXE-Datei ist eine MFC-Anwendung, die dynamisch mit MFC-Bibliotheken sowie andere DLLs verknüpft.)

- Erstellen eine MFC-Erweiterungs-DLL. (Beachten Sie z. B. die speziellen Flags `_AFXEXT` , die beim Erstellen einer MFC-Erweiterungs-DLL verwendet werden)

- Zwei Beispiele für die MFC-Erweiterungs-DLLs. Veranschaulicht die grundlegende Struktur einer MFC-Extension-DLL mit begrenzten Exporten (TESTDLL1) und das andere zeigt eine ganze Klasse-Schnittstelle (TESTDLL2) exportieren.

Die Clientanwendung und alle MFC-Erweiterungs-DLLs müssen die gleiche Version von MFCxx.DLL verwenden. Sie folgen der Konvention von MFC-DLL und geben Sie sowohl eine Debug- und Vertrieb. (/ release) Version von der MFC-Erweiterungs-DLL. Dies ermöglicht die Clientprogramme sowohl Debug-als auch im Einzelhandel Versionen ihrer Anwendungen zu erstellen und verknüpfen Sie sie mit der entsprechenden Debug- oder eine Verkaufsversion aller DLLs.

> [!NOTE]
>  Da C++ Namen mangling und Probleme zu exportieren, kann die Exportliste einer MFC-Erweiterungs-DLL zwischen den Debug- und im-Versionen derselben DLL und DLLs für verschiedene Plattformen unterscheiden. Der Einzelhandel MFCxx.DLL wurde etwa 2000 Einstiegspunkte exportiert; das Debuggen MFCxxD.DLL hat etwa 3000 Einstiegspunkte exportiert.

### <a name="quick-note-on-memory-management"></a>Kurze Anmerkung zur Verwaltung des Arbeitsspeichers

Im Abschnitt "Verwaltung des Arbeitsspeichers," am Ende dieser technischen Hinweis, beschreibt die Implementierung von MFCxx.DLL mit die freigegebene Version von MFC. Die Informationen müssen Sie lediglich eine MFC-Erweiterung zu implementieren, die hier DLL beschriebene kennen.

MFCxx.DLL und alle MFC-Erweiterungs-DLLs in einer Clientanwendung Adressraum geladen werden dieselbe Speicherbelegungsfunktion, ressourcenauslastung und andere "global" MFC-Zustände verwenden, als wären sie in der gleichen Anwendung. Dies ist wichtig, da die MFC - fremde DLL-Bibliotheken und reguläre MFC-DLLs, die statisch mit MFC verknüpft wird genau entgegengesetzt Verfahren, und jede DLL belegt Speicher aus ihren eigenen Speicherpool.

Wenn eine MFC-Erweiterungs-DLL Speicher belegt, kann bei jedem anderen Anwendung zugeordnete Objekt frei, dass der Speicher mischen. Wenn eine Anwendung, die gemeinsam genutzten MFC-Bibliotheken verwendet, abstürzt, wird der Schutz des Betriebssystems außerdem die Integrität anderer MFC-Anwendung, die DLL Freigabe beibehalten.

Auf ähnliche Weise werden andere "global" MFC-Zustände, wie die aktuelle ausführbare Datei beim Laden von Ressourcen aus, auch von der Clientanwendung und allen MFC-Erweiterungs-DLLs sowie MFCxx.DLL selbst gemeinsam genutzt.

### <a name="building-an-mfc-extension-dll"></a>Erstellen eine MFC-Erweiterungs-DLL

Sie können die AppWizard verwenden, um ein MFC-Erweiterungs-DLL-Projekt zu erstellen, und generiert automatisch die entsprechenden Compiler und Linker-Einstellungen. Es wurde auch generieren eine `DllMain` -Funktion, die Sie ändern können.

Wenn Sie ein vorhandenes Projekt in einer MFC-Erweiterungs-DLL konvertieren, beginnen Sie mit den Standardregeln für die Erstellung einer Anwendung, die die freigegebene Version von MFC, dann führen Sie folgende Schritte aus:

- Hinzufügen **/D_AFXEXT** den Compiler-Flags. Wählen Sie im Dialogfeld "Projekteigenschaften" den C-/C++-Knoten. Wählen Sie dann die Kategorie "Präprozessor" ein. Hinzufügen `_AFXEXT` dem Definieren von Makros-Feld, alle Elemente durch Semikolons trennen.

- Entfernen Sie die **/Gy** Compilerschalter. Wählen Sie im Dialogfeld "Projekteigenschaften" den C-/C++-Knoten. Wählen Sie dann die Kategorie "Codegenerierung". Stellen Sie sicher, dass die Option "Funktionslevel-Linking aktivieren" nicht aktiviert ist. Dadurch wird es leichter, Klassen zu exportieren, da der Linker Unreferenzierte Funktionen nicht entfernt werden. Wenn das ursprüngliche Projekt zum Erstellen einer reguläres wird MFC-DLL statisch mit MFC, Änderung verknüpfte der **"/ MT" [d]** -Compileroption verwenden, um **/MD [d]**.

- Erstellen Sie eine Bibliothek exportieren, mit der **/DLL** Option aus, um den LINK. Dadurch wird festgelegt, werden bei der Erstellung eines neuen Ziels, Win32-Dynamic Link Library als des Zieltyps angeben.

### <a name="changing-your-header-files"></a>Ändern der Headerdateien

Das Ziel eine MFC-Erweiterungs-DLL ist in der Regel einige allgemeine Funktionen für eine oder mehrere Anwendungen zu exportieren, die diese Funktion verwenden zu können. Läuft dies auf das Exportieren von Klassen und globale Funktionen, die für Ihre Clientanwendungen verfügbar sind.

Zu diesem Zweck müssen sicherstellen, dass jede der Memberfunktionen wie importieren oder Exportieren nach Bedarf markiert ist. Dies erfordert besondere Deklarationen: `__declspec(dllexport)` und `__declspec(dllimport)`. Wenn Ihre Klassen, die von Clientanwendungen verwendet werden, sollen diese deklariert werden, als `__declspec(dllimport)`. Wenn die MFC-Erweiterungs-DLL selbst erstellt wird, sollten sie als deklariert werden `__declspec(dllexport)`. Darüber hinaus müssen die Funktionen tatsächlich exportiert werden, damit sie die Clientprogramme zur Ladezeit binden.

Verwenden Sie zum Exportieren der gesamte Klasse `AFX_EXT_CLASS` in der Klassendefinition. Dieses Makro wird definiert durch das Framework als `__declspec(dllexport)` beim `_AFXDLL` und `_AFXEXT` definiert ist, aber als definiert `__declspec(dllimport)` beim `_AFXEXT` ist nicht definiert. `_AFXEXT` wie oben beschrieben, wird nur definiert, wenn Sie die MFC-Erweiterungs-DLL zu erstellen. Zum Beispiel:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>Nicht exportieren die gesamte Klasse

In einigen Fällen empfiehlt es sich um nur die einzelnen erforderlichen Member der Klasse zu exportieren. Angenommen, Sie exportieren eine `CDialog`-abgeleitete Klasse sein, benötigen Sie möglicherweise nur um den Konstruktor zu exportieren und die `DoModal` aufrufen. Sie können diese Member, die mit der DLLs exportieren. DEF-Datei, aber Sie können auch `AFX_EXT_CLASS` in ähnelt der Vorgehensweise für die einzelnen Mitglieder, die Sie exportieren möchten.

Zum Beispiel:

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

Wenn Sie dies tun, können Sie ein zusätzliches Problem ausführen, da Sie nicht mehr alle Member der Klasse exportieren. Das Problem ist auf die Weise, die MFC-Makros funktionieren. Einige der MFC Hilfsmakros tatsächlich deklarieren oder definieren Datenelemente. Aus diesem Grund werden diese Datenmember müssen auch aus der DLL exportiert werden.

Die DECLARE_DYNAMIC-Makro wird beispielsweise wie folgt definiert, beim Erstellen einer MFC-Erweiterungs-DLL:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

Die Zeile, beginnt "statische `AFX_DATA`" ist ein statisches Objekt innerhalb der Klasse deklarieren. Diese Klasse ordnungsgemäß zu exportieren und Zugriff auf die Common Language Runtime-Informationen von einem Client. EXE-Datei, müssen Sie diese statische Objekt exportieren. Da die statische Objekt mit dem Modifizierer deklariert wird `AFX_DATA`, müssen Sie nur definieren `AFX_DATA` sein `__declspec(dllexport)` beim Erstellen der DLL und definieren ihn als `__declspec(dllimport)` beim Erstellen der ausführbare Client.

Wie weiter oben erläutert `AFX_EXT_CLASS` ist bereits auf diese Weise definiert. Sie müssen nur neu definieren `AFX_DATA` identisch sein `AFX_EXT_CLASS` Ihrer Klassendefinition.

Zum Beispiel:

```cpp
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

MFC verwendet stets die `AFX_DATA` Symbol für Datenelemente, die innerhalb der Makros definiert, daher kann dieses Verfahren für alle derartigen Szenarien verwendet werden. Z. B. funktioniert DECLARE_MESSAGE_MAP.

> [!NOTE]
> Wenn Sie anstelle von ausgewählten Member der Klasse die gesamte Klasse exportieren, werden automatisch statischen Datenmember exportiert.

Sie können das gleiche Verfahren verwenden, so exportieren Sie automatisch die `CArchive` Extraktionsoperator für Klassen, die DECLARE_SERIAL und IMPLEMENT_SERIAL-Makros zu verwenden. Exportieren Sie den Archiv-Operator, indem Sie Klammern die Klassendeklarationen (befindet sich in der. H-Datei) mit dem folgenden Code:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-afxext"></a>Einschränkungen von _AFXEXT

Sie können die _**AFXEXT** Präprozessor-Symbol für die MFC-Erweiterungs-DLLs, solange Sie nicht über mehrere Ebenen von MFC-Erweiterungs-DLLs verfügen. Wenn Sie MFC-Erweiterungs-DLLs, die aufrufen oder das Ableiten von Klassen in Ihren eigenen MFC-Erweiterungs-DLLs, die dann von den MFC-Klassen abgeleitet werden verfügen, müssen Sie eigene Präprozessorsymbol verwenden, um Mehrdeutigkeiten zu vermeiden.

Das Problem besteht darin, in Win32, müssen Sie explizit deklarieren, alle Daten als `__declspec(dllexport)` ist dies über eine DLL exportiert werden und `__declspec(dllimport)` ist dies aus einer DLL importiert werden. Beim Definieren von `_AFXEXT`, die MFC-Header verwenden, stellen sicher, dass `AFX_EXT_CLASS` ordnungsgemäß definiert ist.

Wenn Sie verfügen über mehrere Ebenen, ein Symbol z. B. `AFX_EXT_CLASS` ist nicht ausreichend, da eine MFC-Erweiterungs-DLL kann werden Exportieren von neuen Klassen als auch andere Klassen aus einer anderen MFC-Erweiterungs-DLL importieren. Um dieses Problem zu beheben, verwenden Sie ein spezielles Präprozessorsymbol, das angibt, dass Sie die DLL selbst im Vergleich zur Verwendung der DLL erstellen. Beispiel: Angenommen Sie, zwei MFC-Erweiterungs-DLLs, eine DLL- und B.DLL. Jeder exportieren bzw. einige Klassen in A.H bzw. B.H. B.DLL verwendet die Klassen von A.DLL. Die Headerdateien würde etwa wie folgt aussehen:

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

Wenn A.DLL erstellt wird, wird er erstellt, mit **/DA_IMPL** und wenn B.DLL erstellt wird, wird er erstellt, mit **/DB_IMPL**. Getrennte Symbole für jede DLL-Datei verwenden, CExampleB exportiert wird, und beim Erstellen von B.DLL CExampleA importiert. CExampleA wird beim Erstellen von A.DLL beim exportiert und importiert von B.DLL (oder einen anderen Client) verwendet.

Diese Art von Überlagerung kann nicht durchgeführt werden, bei Verwendung die integrierten `AFX_EXT_CLASS` und `_AFXEXT` Präprozessorsymbole. Das oben beschriebene Verfahren löst dieses Problem in einer Weise, die nicht im Gegensatz zu die der Mechanismus MFC selbst verwendet werden soll, wenn der OLE-Datenbank und Netzwerk-MFC-Erweiterungs-DLLs zu erstellen.

### <a name="not-exporting-the-entire-class"></a>Nicht exportieren die gesamte Klasse

In diesem Fall müssen Sie besondere Sorgfalt walten, wenn Sie keine ganze Klasse exportieren. Sie müssen sicherstellen, dass die erforderlichen Datenelemente, die von den MFC-Makros erstellt ordnungsgemäß exportiert werden. Dies ist möglich durch die erneute Definition `AFX_DATA` in Ihre spezifische Klasse-Makro. Dies soll jedes Mal erfolgen Sie nicht die gesamte Klasse exportieren.

Zum Beispiel:

```cpp
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
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

Folgendes ist die genaue Code, den Sie in der main-Quelldatei, für die MFC-Erweiterungs-DLL platzieren sollten. Es auch nach der Standard umfasst. Beachten Sie, dass wenn Sie AppWizard verwenden, um die Startdateien für eine MFC-Erweiterungs-DLL zu erstellen, er gibt eine `DllMain` für Sie.

```cpp
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

Der Aufruf von `AfxInitExtensionModule` erfasst die Common Language Runtime-Klassen-Module (`CRuntimeClass` Strukturen) sowie die Objektfactory (`COleObjectFactory` Objekte) für die Verwendung später, wenn die `CDynLinkLibrary` Objekt erstellt wird. (Optional) den Aufruf `AfxTermExtensionModule` können MFC so bereinigen Sie die MFC-Erweiterungs-DLL wird jeder Prozess getrennt (Dies ist der Fall, wenn der Prozess beendet wird oder die DLL entladen wird, als Ergebnis des eine `FreeLibrary` aufrufen) aus der MFC-Erweiterungs-DLL. Da die meisten MFC-Erweiterungs-DLLs nicht dynamisch geladen werden werden (in der Regel verknüpft sind über ihre Importbibliotheken), den Aufruf von `AfxTermExtensionModule` ist in der Regel nicht erforderlich.

Wenn die Anwendung lädt und dynamisch frei von MFC-Erweiterungs-DLLs, müssen Sie unbedingt Aufrufen `AfxTermExtensionModule` wie oben gezeigt. Achten Sie auch mit `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle von Win32-Funktionen `LoadLibrary` und `FreeLibrary`) Wenn Ihre Anwendung mehrere Threads verwendet, oder wenn sie dynamisch eine MFC-Erweiterungs-DLL geladen wird. Mithilfe von `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass der starten und Herunterfahren Code, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL geladen und entladen wird den globalen MFC-Status nicht beschädigt ist.

Die Headerdatei AFXDLLX. H enthält spezielle Definitionen für Strukturen, die in MFC-Erweiterungs-DLLs, z. B. die Definition für die verwendete `AFX_EXTENSION_MODULE` und `CDynLinkLibrary`.

Die globale *ExtensionDLL* muss wie gezeigt deklariert werden. Im Gegensatz zu den 16-Bit-Version von MFC können Sie Speicher zuordnen und während dieser Zeit MFC-Funktionen aufrufen, da MFCxx.DLL vollständig, mit der Zeit initialisiert wurde Ihrer `DllMain` aufgerufen wird.

### <a name="sharing-resources-and-classes"></a>Gemeinsame Nutzung von Ressourcen und Klassen

Einfache MFC-Erweiterungs-DLLs müssen nur wenige mit geringer Bandbreite-Funktionen in der Clientanwendung und nicht mehr exportieren. Mehr als intensive Benutzeroberflächen-DLLs sollten Ressourcen und C++-Klassen in der Clientanwendung zu exportieren.

Der Export von Ressourcen erfolgt über eine Ressourcenliste. Jede Anwendung ist eine einzeln verknüpfte Liste von `CDynLinkLibrary` Objekte. Wenn für eine Ressource zu suchen, die meisten MFC-standardimplementierungen, die Ressourcen zu laden sehen Sie sich zunächst die aktuellen Ressourcenmodul (`AfxGetResourceHandle`) und Walk wurde nicht gefunden, wenn die Liste der `CDynLinkLibrary` Objekte, die beim Laden der angeforderten Ressource.

Dynamische Erstellung von C++-Objekten, die eine C++-Klasse benannt ist ähnlich. Der Mechanismus zur Deserialisierung von MFC-Objekt, dass alle muss die `CRuntimeClass` -Objekte registriert, sodass es durch die dynamische Erstellung von C++-Objekt des erforderlichen Typs anhand der zuvor gespeicherten nachvollziehen zu kann.

Wenn Sie möchten die Clientanwendung Klassen in der MFC-Erweiterungs-DLL zu verwenden, sind `DECLARE_SERIAL`, müssen Sie so exportieren Sie Ihre Klassen, um die an die Clientanwendung angezeigt werden. Dies auch geschieht durch Durchlaufen der `CDynLinkLibrary` Liste.

Im Fall von im MFC Advanced Concepts-Beispiel [DLLHUSK](../visual-cpp-samples.md), die Liste sieht wie folgt:

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

Die MFCxx.DLL befindet sich letzter in der Ressourcen- und Klassenliste. MFCxx.DLL enthält alle MFC-Standardressourcen, einschließlich der eingabeaufforderungen aller Standardbefehls-IDs für die. Legen Sie das Element am Ende der Liste kann DLLs und die Clientanwendung selbst keine eigene Kopie der MFC-Standardressourcen, aber auf basieren auf den freigegebenen Ressourcen in MFCxx.DLL stattdessen.

Zusammenführen von Ressourcen und Klassennamen aller DLLs mit der Clientanwendung Namespace hat den Nachteil, die Sie vorsichtig sein, welche IDs oder Namen, die Sie auswählen. Sie können natürlich deaktivieren diese Funktion durch den Export nicht entweder Ihre Ressourcen oder `CDynLinkLibrary` Objekt an die Clientanwendung. Die [DLLHUSK](../visual-cpp-samples.md) Beispiel verwaltet den Namespace für gemeinsam genutzte Ressource durch mehrere Headerdateien. Finden Sie unter [technischen Hinweis 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) Weitere Tipps zum Arbeiten mit freigegebenen Dateien.

### <a name="initializing-the-dll"></a>Initialisieren der DLL

Wie oben erwähnt, sollten Sie in der Regel erstellen Sie eine `CDynLinkLibrary` Objekt, um Ihre Ressourcen und Klassen in der Clientanwendung zu exportieren. Sie benötigen, geben Sie einen exportierten Einstiegspunkt für die DLL nicht initialisieren. Minimal, dies ist eine "void" Routine, die keine Argumente akzeptiert und gibt nichts zurück, aber es kann beliebig sein.

Wenn Sie diesen Ansatz verwenden, muss jede Clientanwendung, die die DLL verwenden möchte Initialisierungsroutine, aufrufen. Sie können dies auch zuordnen `CDynLinkLibrary` -Objekt in Ihrer `DllMain` nur nach dem Aufruf `AfxInitExtensionModule`.

Die Initialisierungsroutine erstellen muss eine `CDynLinkLibrary` Objekt in der aktuellen Anwendung Heap angeschlossen an die MFC-Erweiterungs-DLL-Informationen. Dies kann durch Folgendes geschehen:

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

Die Namen der Routine *InitXxxDLL* in diesem Beispiel kann beliebig sein. Es muss nicht werden **Extern "C"**, aber dies der Fall ist der Exportliste angezeigt, die einfacher zu verwalten.

> [!NOTE]
> Wenn Sie die MFC-Erweiterungs-DLL von einem regulären MFC-DLL verwenden, müssen Sie diese Initialisierungsfunktion exportieren. Diese Funktion muss von den regulären MFC-DLL aufgerufen werden, vor der Verwendung von alle MFC-Erweiterungs-DLL-Klassen oder Ressourcen.

### <a name="exporting-entries"></a>Exportieren von Einträgen

Die einfachste Möglichkeit, die Klassen exportieren ist die Verwendung `__declspec(dllimport)` und `__declspec(dllexport)` für jede Klasse und die globale Funktion, die Sie exportieren möchten. Dies macht es viel einfacher, aber es ist weniger effizient als die Benennung von jeden Einstiegspunkt (siehe unten), da haben Sie weniger Kontrolle über welche Funktionen exportiert werden, und Sie können nicht die Funktionen anhand der Ordinalzahl exportieren. TESTDLL1 und TESTDLL2 verwenden diese Methode, um ihre Einträge zu exportieren.

Eine effizientere Methode (und die Methode, die von MFCxx.DLL verwendet) werden jeder Eintrag manuell zu exportieren, benennen Sie jeden Eintrag in der. DEF-Datei. Da wir selektive Exporte aus unserer (d. h. nicht alle) DLL exportieren, müssen wir entscheiden, welche bestimmten Schnittstellen wir exportieren möchten. Dies ist schwierig, da Sie die ergänzten Namen für den Linker, in Form von Einträgen in angeben müssen der. DEF-Datei. Alle C++-Klassen nicht exportiert werden, es sei denn, Sie unbedingt einen symbolischen Link dafür verfügen.

Wenn Sie versucht haben, Exportieren von C++ mit Klassen ein. DEF-Datei, bevor Sie ein Tool, um diese Liste automatisch generieren entwickeln möchten. Dies kann erfolgen über einen Link von einem zweistufigen Prozess. Verknüpfen Sie die DLL einmal mit keine Exporte und ermöglichen den Linker an generieren ein. MAP-Datei. Die. MAP-Datei kann verwendet werden, um eine Liste der Funktionen, die exportiert werden soll, zu generieren, damit mit einigen neu anordnen, sie verwendet werden kann, generieren Sie Ihre EXPORT-Einträge für Ihre. DEF-Datei. Die Exportliste für MFCxx.DLL und die OLE und der Datenbank-MFC-Erweiterungs-DLLs, mehrere Tausend bezüglich Anzahl, wurde mit solchen Prozess generiert, (obwohl es nicht vollkommen automatisch und erfordert einige manuell alle einmal eine Optimierung).

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp im Vergleich zu CDynLinkLibrary

Eine MFC-Erweiterungs-DLL verfügt nicht über eine `CWinApp`-abgeleitetes Objekt selbst; stattdessen müssen sie gemeinsam mit der `CWinApp`-abgeleitete Objekt der Clientanwendung. Dies bedeutet, dass die Clientanwendung die Haupt-Meldungsverteilschleife, die Leerlaufschleife usw. besitzt.

Wenn die MFC-Erweiterungs-DLL zusätzliche Daten für jede Anwendung zu verwalten muss, können Sie eine neue Klasse von ableiten `CDynLinkLibrary` und erstellen Sie ihn in das InitXxxDLL Routine oben beschrieben. Die DLL kann bei der Ausführung Überprüfen der aktuellen Anwendung Liste `CDynLinkLibrary` Objekten, die für die jeweilige MFC-Erweiterungs-DLL gesucht.

### <a name="using-resources-in-your-dll-implementation"></a>Verwenden von Ressourcen in der DLL-Implementierung

Wie bereits erwähnt, führt die standardauslastung für die Ressource die Liste der `CDynLinkLibrary` Objekte, die nach der ersten exe- oder DLL, die die angeforderte Ressource verfügt. Alle MFC-APIs sowie alle der interne Code verwendet `AfxFindResourceHandle` , durchlaufen die Ressourcenliste finden Sie alle Ressourcen, unabhängig davon, in dem sie gespeichert werden kann.

Wenn Sie nur Ressourcen von einer bestimmten Stelle laden möchten, verwenden Sie die APIs `AfxGetResourceHandle` und `AfxSetResourceHandle` das alte Handle zu speichern und das neue Handle festzulegen. Achten Sie darauf, dass Sie das alte Ressourcenhandle wiederherstellen, bevor Sie zur Clientanwendung zurückkehren. Das Beispiel TESTDLL2 verwendet diesen Ansatz für explizites Laden eines Menüs.

Das Durchlaufen der Liste hat jedoch den Nachteil, dass die Suche etwas langsamer ist und dass die Ressourcen-ID-Bereiche verwaltet werden müssen. Es hat den Vorteil, dass eine Clientanwendung, die mit mehreren MFC-Erweiterungs-DLLs verknüpft alle bereitgestellte DLL-Ressourcen verwenden kann, ohne die DLL-Instanzenhandle angegeben. `AfxFindResourceHandle` ist eine API, die bei der Suche nach einer bestimmten Übereinstimmung die Ressourcenliste durchläuft. Sie verwendet den Ressourcennamen und -typ als Parameter und gibt das zuerst ermittelte Ressourcenhandle (oder NULL) zurück.

##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> Beim Schreiben einer Anwendung, die die DLL-Version verwendet.

### <a name="application-requirements"></a>Anwendungsanforderungen

Eine Anwendung, die freigegebene Version von MFC verwendet, muss einige einfache Regeln ausführen:

- Sie benötigen eine `CWinApp` Objekt aus, und führen Sie die Standardregeln für ein Nachrichtensystem.

- Sie müssen mit einem Satz von erforderlichen Compilerflags (siehe unten) kompiliert werden.

- Sie müssen mit den Importbibliotheken MFCxx verknüpfen. Wenn Sie die erforderlichen Compilerflags festlegen, bestimmen die MFC-Header zum Zeitpunkt der Verknüpfung die Bibliothek, die mit die Anwendung verknüpft werden sollen.

- Führen Sie die ausführbare Datei muss MFCxx.DLL auf dem Pfad oder im Windows-Systemverzeichnis.

### <a name="building-with-the-development-environment"></a>Erstellen mit der Entwicklungsumgebung

Wenn Sie mit den meisten von den Standardwerten der internen Makefile verwenden, können Sie einfach das Projekt zum Erstellen der DLL-Version ändern.

Die folgende Schritte wird davon ausgegangen, dass Sie eine ordnungsgemäß funktionierende MFC-Anwendung mit NAFXCWD verknüpft haben. LIB (für Debug) "und" NAFXCW ". LIB (für den Einzelhandel), und Sie möchten konvertieren, um die freigegebene Version der MFC-Bibliothek verwenden. Sie die Visual C++-Umgebung ausgeführt werden und eine interne-Projektdatei.

1. Auf der **Projekte** Menü klicken Sie auf **Eigenschaften**. In der **allgemeine** Seite **Projektstandards**, legen Sie auf die Microsoft Foundation Classes **MFC in einer gemeinsam genutzten DLL verwenden** (MFCxx(d).dll).

### <a name="building-with-nmake"></a>Erstellen von Builds mit NMAKE

Wenn Sie die externes Makefile-Funktion von Visual C++-Komponente verwenden oder direkt NMAKE verwenden, müssen Sie Ihre Makefile zur Unterstützung von Compiler- und Linkeroptionen bearbeiten

Erforderliche Compilerflags:

- **/ D_AFXDLL/MD**
   **/D_AFXDLL**

Die MFC-Standardheader benötigen dieses Symbol definiert werden:

- **/ MD** die Anwendung muss die DLL-Version der C-Laufzeitbibliothek verwenden

Alle anderen Compilerflags führen Sie die MFC-Standardeinstellungen (z. B. _DEBUG für Debugbuilds).

Bearbeiten Sie die Linker-Liste der Bibliotheken. Ändern Sie NAFXCWD. Um MFCxxD.LIB LIB, und ändern Sie NAFXCW. LIB MFCxx.LIB. Ersetzen Sie dies LIBC. LIB mit MSVCRT. LIB. Wie bei jeder anderen MFC-Bibliothek ist es wichtig, dass MFCxxD.LIB platziert wird **vor** C-Laufzeitbibliotheken.

Fügen Sie optional hinzu **/D_AFXDLL** auf Ihre Verkaufsversionen und Debugbuilds Ressource Compileroptionen (diejenige, die tatsächlich die Ressourcen mit kompiliert **/r**). Auf diese Weise die endgültige ausführbare Datei durch die Freigabe der Ressourcen, die in den MFC-DLLs vorhanden sind kleiner.

Eine vollständige Neuerstellung ist erforderlich, nachdem diese Änderungen vorgenommen wurden.

### <a name="building-the-samples"></a>Erstellen der Beispiele

Die meisten Programme die MFC-Beispiel können von Visual C++ oder mit einem freigegebenen NMAKE-kompatiblen MAKEFILE über die Befehlszeile erstellt werden.

Um solche Beispiele zur Verwendung von MFCxx.DLL zu konvertieren, können Sie laden die. MAK-Datei in Visual C++-Komponente, und legen Optionen für das Projekt aus, wie oben beschrieben. Wenn Sie den NMAKE-Build verwenden, können Sie angeben "AFXDLL = 1" auf der NMAKE-Befehlszeile und, erstellt das Beispiel mithilfe der gemeinsam genutzte MFC-Bibliotheken.

Im MFC Advanced Concepts-Beispiel [DLLHUSK](../visual-cpp-samples.md) mit der MFC-DLL-Version erstellt wurde. Dieses Beispiel veranschaulicht das nicht nur zum Erstellen einer Anwendung mit MFCxx.DLL verknüpft, aber darüber hinaus veranschaulicht es andere Funktionen der MFC-DLL Packaging-Option wie MFC-Erweiterungs-DLLs, die weiter unten in diesem technischen Hinweis beschrieben.

### <a name="packaging-notes"></a>Anmerkungen zu dieser Version paketerstellung

Die Verkaufsversion von die DLLs (MFCxx [U]. DLL) beliebig weitervertrieben werden. Die Debugversion von die DLLs sind nicht beliebig weitervertrieben und sollte nur während der Entwicklung Ihrer Anwendung verwendet werden.

Die Debug-DLLs werden bereitgestellt, mit Debuginformationen. Mithilfe von Visual C++-Debugger können Sie die Ausführung Ihrer Anwendung als auch für die DLL verfolgen. Die Release-DLLs (MFCxx [U]. DLL) werden keine Debuginformationen.

Wenn Sie anpassen oder die DLLs neu zu erstellen, sollten Sie diese etwas als "MFCxx" der MFC-SRC-Datei MFCDLL aufrufen. MAK Buildoptionen beschreibt und enthält die Logik für die DLL umbenennen. Umbenennen von Dateien ist erforderlich, da diese DLLs möglicherweise viele MFC-Anwendungen gemeinsam genutzt werden. Mit der benutzerdefinierten Version von MFC-DLLs ersetzen können diese auf dem System installiert eine andere MFC-Anwendung, die mit der gemeinsam genutzte MFC-DLLs beeinträchtigt werden.

Neuerstellen der MFC-DLLs wird nicht empfohlen.

##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> Wie wird die MFCxx.DLL implementiert.

Im folgende Abschnitt wird beschrieben, wie die MFC-DLL (MFCxx.DLL und MFCxxD.DLL) implementiert wird. Zu verstehen, dass die Informationen finden Sie hier auch nicht ist wichtig, wenn Sie möchten die MFC-DLL in Ihrer Anwendung verwenden. Hier die Details sind nicht wichtig, um zu verstehen, wie Sie eine MFC-Erweiterungs-DLL zu schreiben, aber Grundlegendes zu dieser Implementierung können Sie leichter Schreiben Ihrer eigenen DLL.

### <a name="implementation-overview"></a>Übersicht über die Implementierung

Die MFC-DLL ist wirklich ein Sonderfall, der eine MFC-Erweiterungs-DLL an, wie oben beschrieben. Es verfügt über eine sehr große Anzahl von Exporten, die für eine große Anzahl von Klassen. Es gibt einige zusätzliche Möglichkeiten in der MFC-DLL, die noch mehr als eine reguläre MFC-Erweiterungs-DLL spezielle erleichtern.

### <a name="win32-does-most-of-the-work"></a>Win32 übernimmt den Großteil der Arbeit

Die 16-Bit-Version von MFC erforderlich, eine Reihe von speziellen Techniken sowie die pro-app-Daten auf dem Stapel-Segment, spezielle Segmente erstellt, indem einige 80 x 86-Assemblycode, pro Prozess Ausnahme Kontexten und andere Techniken. Win32 unterstützt direkt pro-Verarbeiten von Daten in eine DLL, die in den meisten Fällen erwünscht. In den meisten Fällen ist die MFCxx.DLL nur NAFXCW. LIB, die in eine DLL-Datei verpackt. Wenn Sie die MFC-Quellcode betrachten, finden Sie nur sehr wenige #ifdef _AFXDLL, da es sich nur sehr wenige spezielle Fälle, die vorgenommen werden müssen. Die besondere Fälle, es sind speziell für den Umgang mit Win32 auf Windows 3.1 (auch bekannt als Win32s). Win32s ist nicht prozessspezifisch DLL Supportdaten direkt also die MFC-DLL den threadlokalen Speicher (TLS) Win32-APIs zum Abrufen der lokalen Verarbeitung von Daten verwenden müssen.

### <a name="impact-on-library-sources-additional-files"></a>Auswirkungen auf die Bibliothekquellen, zusätzliche Dateien

Die Auswirkungen der **_AFXDLL** -Version auf dem normalen MFC-Klasse Bibliothekquellen und Headern ist relativ unbedeutend. Es ist eine spezielle Version-Datei (AFXV_DLL. H) sowie eine zusätzliche Headerdatei (AFXDLL_. H) enthalten durch die wichtigsten AFXWIN. H-Header. Die AFXDLL_. H-Header enthält den `CDynLinkLibrary` -Klasse und weitere Implementierungsdetails beider `_AFXDLL` Anwendungen und MFC-Erweiterungs-DLLs. Die AFXDLLX. H-Header wird bereitgestellt, für die Erstellung von MFC-Erweiterungs-DLLs (Informationen finden Sie weiter oben).

Die reguläre Quellen aus, für die MFC-Bibliothek in MFC SRC haben einige zusätzlichen bedingten Code unter der `_AFXDLL` #ifdef. Eine zusätzliche Quelldatei (DLLINIT. CPP) enthält die zusätzlichen Initialisierungscode einer DLL und anderen "kitt" für die freigegebene Version von MFC.

Um die freigegebene Version von MFC zu erstellen, werden zusätzliche Dateien bereitgestellt. (Einzelheiten finden Sie unten auf das die DLL zu erstellen.)

- Zwei. DEF-Dateien werden verwendet, für die MFC-DLL-Einstiegspunkte für Debug (MFCxxD.DEF) exportieren und Releaseversionen (MFCxx.DEF) der DLL.

- Ein. RC-Datei (MFCDLL. RC) enthält alle MFC-Standardressourcen und eine VERSIONINFO-Ressource für die DLL an.

- EIN. CLW-Datei (MFCDLL. CLW) wird ermöglicht, durchsuchen die MFC-Klassen mit Klassen-Assistenten bereitgestellt. Hinweis: Diese Funktion ist nicht spezifisch für die DLL-Version von MFC.

### <a name="memory-management"></a>Speicherverwaltung

Eine Anwendung mit MFCxx.DLL verwendet eine allgemeine speicherbelegung von MSVCRTxx.DLL, die gemeinsam genutzten DLL der C-Laufzeit bereitgestellt. Die Anwendung, alle MFC-Erweiterungs-DLLs und sowie die MFC-DLLs selbst verwenden diese Zuweisung gemeinsam genutzten Speicher. Gemeinsam genutzte DLL für speicherbelegung verwenden, können die MFC-DLLs Arbeitsspeicher zuordnen, die später von der Anwendung oder umgekehrt freigegeben wird. Da die Anwendung und die DLL auf die gleiche Zuweisung verwenden müssen, sollten Sie nicht überschreiben, auf der globalen C++ **new-Operator** oder **Delete-Operator**. Die gleichen Regeln gelten für den Rest der C-Laufzeitspeicher Zuordnung Routinen (z. B. **"malloc"**, **Realloc**, **kostenlose**, usw.).

### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>Ordnungszahlen "und" Klasse "__declspec(dllexport)" "" und "DLL-Namen

Wir verwenden nicht die `class` **__declspec(dllexport)** Funktionen des C++-Compilers. Stattdessen ist eine Liste der Exporte in der Klasse Bibliothekquellen (MFCxx.DEF und MFCxxD.DEF) enthalten. Nur diese ausgewählten Satz von Einstiegspunkten (Funktionen und Daten) werden exportiert. Andere Symbole, z. B. private Implementierung von MFC-Funktionen oder Klassen werden nicht exportiert alle Exporte nach Ordnungszahl ohne einen Zeichenfolgennamen in dieser Tabelle erhält vom residenten oder nicht-residenten fertig sind.

Mithilfe von `class` **__declspec(dllexport)** möglicherweise eine gute Alternative für die Erstellung kleinerer DLLs, aber bei einer großen DLL wie MFC, der Standardwert exportieren Mechanismus hat, Effizienz und Kapazität Grenzwerte.

Was dies bedeutet, dass wir eine große Menge an Funktionalität in der Version MFCxx.DLL Verpacken kann, die nur ca. 800 KB ohne viel Ausführung beeinträchtigen oder ladegeschwindigkeit ist. MFCxx.DLL hätte 100K größere dieses Verfahren nicht der Fall war verwendet. Dies können sie zudem weitere Einstiegspunkte am Ende hinzufügen der. DEF-Datei, um einfache versionsverwaltung zu ermöglichen, ohne Beeinträchtigung der Geschwindigkeit und Größe Effizienz durch die Ordinalzahl zu exportieren. Hauptversion Revisionen in der MFC-Klassenbibliothek ändert den Namen der Bibliothek. D. h. MFC30. DLL-Datei ist die redistributable-DLL, Version 3.0 der MFC-Klassenbibliothek enthält. Ein Upgrade dieser DLL, z. B. in einer hypothetischen 3.1 MFC-DLL MFC31 benannt werden sollen. DLL stattdessen. In diesem Fall, wenn Sie ändern, dass den MFC-Quellcode, um eine benutzerdefinierte Version der MFC-DLL zu erstellen, verwenden Sie einen anderen Namen (und vorzugsweise ohne "MFC" im Namen).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
