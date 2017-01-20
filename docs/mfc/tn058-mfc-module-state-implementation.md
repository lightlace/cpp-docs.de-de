---
title: "TN058: MFC-Modulzustandsimplementierung"
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
  - "vc.mfc.implementation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Modulzustände"
  - "MFC [C++], Verwalten der Zustandsdaten"
  - "Modulzustände [C++], Verwalten der Zustandsdaten"
  - "Modulzustände [C++], Wechsel"
  - "Prozessstatus [C++]"
  - "Threadzustand [C++]"
  - "TN058"
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# TN058: MFC-Modulzustandsimplementierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser technische Hinweis beschreibt die Implementierung von MFC\-"Modulzustands" Konstrukten.  Ein Verständnis der Modulzustandsimplementierung ist für die Anwendung der MFC\-gemeinsamen genutzter DLLs von einem prozessinternen wichtig Server der DLL \(oder OLE\).  
  
 Bevor Sie diesen Hinweis lesen, können Sie "Verwalten der Statusdaten von MFC\-Modulen" in [Erstellen neuer Dokumente, Windows und von Ansichten](../mfc/creating-new-documents-windows-and-views.md).  Dieser Artikel enthält wichtige Verwendungsinformationen und Übersichtsinformationen zu diesem Thema.  
  
## Übersicht  
 Es gibt drei Arten MFC\-Zustandsinformationen: Modulzustand, Prozess\-Zustand und Threadzustand.  Manchmal können diese Zustandstypen kombiniert werden.  Beispielsweise sind Handlezuordnungen MFC Modullokale variable und Threadlokale Variablenargument.  Dadurch gelten zwei unterschiedlichen Modulen, um verschiedene Zuordnungen in einem der Threads verfügen.  
  
 Prozesszustand und Threadzustand sind ähnlich.  Diese Punkte, Datenelemente sind, die traditionell globale Variablen wurden, aber noch Anforderung, einen angegebenen Prozess oder einen Thread für eine ordnungsgemäße Win32s\-Unterstützung oder für richtige Multithreadingunterstützung bestimmt sein.  Welche Kategorie ein bestimmtes Datenelement in Anpassen, hängt von diesem Element und die gewünschten Semantik hinsichtlich der Prozess\- und Threadgrenzen ab.  
  
 Modulzustand ist insofern einmalig, dass er tatsächlich globalen Zustand enthalten oder angeben kann, der Prozesslokale Threadlokale Variable oder Variable ist.  Außerdem kann es schnell umgeschaltet werden.  
  
## Modulzustands\-Umschalten  
 Jeder Thread enthält einen Zeiger z "aktuelle" oder "Aktiv" Modulzustand \(erwartungsgemäß, Zeiger ist der Teil von lokalem Zustand Threads MFC\).  Dieser Zeiger wird, wenn der Thread der Ausführung eine Modulgrenze wird, wie in eine Anwendung ein Aufruf OLE\-Steuerelement oder DLL, geändert oder in ein OLE\-Steuerelement Aufrufen zurück in eine Anwendung.  
  
 Der aktuellen Modulzustand umgeschaltet wird, indem **AfxSetModuleState** aufruft.  In den meisten Fällen arbeiten Sie nie direkt die API.  MFC in vielen Fällen wird für Sie auf \(bei WinMain, BEI OLE\-Einstiegspunkten, bei **AfxWndProc**, z.\). Dies wird in aller Komponenten, die Sie schreiben, indem Sie speziellen statisch in **WndProc** verknüpfen und spezielles `WinMain` abgeschlossen \(oder `DllMain`\) die bekannt ist, welcher Modulzustand aktuell sein sollte.  Sie können diesen Code finden, indem Sie DLLMODUL.CPP oder APPMODUL.CPP im Verzeichnis MFC\\SRC berücksichtigen.  
  
 Es ist nur selten, den Modulzustand festlegen und ihn dann hinter nicht festlegen möchten.  Meistens möchten Sie eigenen als aktuellen Modulzustand "" und drücken dann, wenn Sie fertig "lauten, holen Sie die ursprüngliche" Kontextrückseite.  Dies wird durch Makro\- [korrekten](../Topic/AFX_MANAGE_STATE.md) und die spezielle Klasse **AFX\_MAINTAIN\_STATE** vorgenommen.  
  
 `CCmdTarget` weist besondere Funktionen zur Unterstützung des Modulzustandsumschaltens.  Insbesondere ist `CCmdTarget` die Stammklasse, für die OLE\-Automatisierung und OLE\-COM\-Einstiegspunkte verwendet wird.  Wie jeder andere Einstiegspunkt, der dem System verfügbar gemacht wird, müssen diese Einstiegspunkte den korrekten Modulzustand festlegen.  Wie kennt angegebenes `CCmdTarget`, was der "richtige" Modulzustand werden soll?  Die Antwort wird, dass dem "speichert" was "aktuelle" Modulzustand, wenn dieser erstellt wird, so ist, dass es den aktuellen Modulzustand festlegen "kann auf den erinnerter" Wert, wenn es später aufgerufen wird.  Daher ist der Modulzustand, dem ein bestimmtes `CCmdTarget`\-Objekt zugeordnet ist, mit der Modulzustand, der aktuelle Datensatz war, als das Objekt erstellt wurde.  Erstellen Sie ein einfaches Beispiel für Laden eines INPROC\-Servers, zum Erstellen eines Objekts und das Aufrufen ihrer Methoden.  
  
1.  Die DLL wird von OLE mit **LoadLibrary** geladen.  
  
2.  **RawDllMain** ist zuerst aufgerufen.  Es legt den Modulzustand auf dem bekannten statischen Modulzustand für die DLL fest.  Aus diesem Grund wird **RawDllMain** statisch mit der DLL verknüpft.  
  
3.  Der Konstruktor für die Klassenfactory, die mit diesem Objekt zugeordnet wird, wird aufgerufen.  `COleObjectFactory` ist von `CCmdTarget` abgeleitet und infolgedessen, speichert es, in welchem Modulzustand sie instanziiert wurde.  Dies ist wichtig Wenn die Klassenfactory aufgefordert wird, Objekte zu erstellen, weiß jedoch nun, welcher Modulzustand, um der aktuellen zu machen.  
  
4.  `DllGetClassObject` wird aufgerufen, um der Klassenfactory zu erhalten.  MFC durchsucht die Klassenfactoryliste, die diesem Modul zugeordnet ist und gibt diese zurück.  
  
5.  **COleObjectFactory::XClassFactory2::CreateInstance** aufgerufen wird.  Bevor sie das Objekt erstellt und ihn zurückgibt, legt dieser Funktion den Modulzustand auf den Modulzustand fest, der in Schritt 3 \(der aktuelle Datensatz war, der aktuelle Datensatz war, als `COleObjectFactory` instanziiert wurde\).  Dies wird in [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md) erreicht.  
  
6.  Wenn das Objekt erstellt wird, ist es auch eine `CCmdTarget` Ableitung und genauso \- `COleObjectFactory`, die gespeichert wird, die aktiv war Modulzustand, sodass führt dieses neue Objekt.  Jetzt weiß das Objekt, welcher davon Modulzustand, wenn sie aufgerufen wird.  
  
7.  Der Client ruft eine Funktion für den OLE\-COM\-Objekt auf, das von seinem Aufruf `CoCreateInstance` hat.  Wenn das Objekt aufgerufen wird, wird mit `METHOD_PROLOGUE`, um den Modulzustand wechseln, wie eine `COleObjectFactory` veranschaulicht.  
  
 Wie Sie sehen, wird der Modulzustand von Objekt zu Objekt zurückübertragen, während sie erstellt werden.  Es ist wichtig, den Modulzustand entsprechend festlegen zu lassen.  Wenn nicht festgelegt ist, kann die DLL möglicherweise oder COM\-Objekt interagieren kann nicht mit einer MFC\-Anwendung, die das Aufrufen ist, die sich möglicherweise nicht in der Lage, ihre eigenen Ressourcen zu suchen oder auf andere elende Arten aus.  
  
 Beachten Sie, dass bestimmte Arten von DLLs, speziell "MFC\-Erweiterungs\-" DLLs nicht den Modulzustand in ihrem **RawDllMain** wechseln \(tatsächlich, haben sie normalerweise nicht einmal **RawDllMain**\).  Dies ist, da diese Elemente werden, um sich zu verhalten "als ob" sie tatsächlich in der Anwendung vorhanden waren, die sie verwendet.  Sie sind sehr viel Teil der Anwendung, die ausgeführt wird und es die Absicht ist Ändern dass der globale Status der Anwendung.  
  
 OLE\-Steuerelemente und anderen DLLs können sehr unterschiedlich.  Sie möchten nicht den Zustand der aufrufenden Anwendung ändern; die Anwendung, die sie aufgerufen wird, ist möglicherweise nicht einmal eine MFC\-Anwendung und und so liegt möglicherweise kein Zustand zu ändern, selbst.  Dies ist der Grund dafür, dass das Modulzustandsumschalten frei erfunden wurde.  
  
 Bei exportierten Funktionen aus einer DLL, z einer, die ein Dialogfeld in der DLL wird, müssen Sie den folgenden Code am Anfang der Funktion hinzufügen:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Dies tauscht den Modulzustand mit dem Zustand aus, der über [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) auf das Ende des aktuellen Bereichs zurückgegeben wird.  
  
 Probleme mit Ressourcen in DLLs treten auf, wenn das Makro `AFX_MODULE_STATE` nicht verwendet wird.  Standardmäßig verwendet MFC wie Ressourcenhandle der Hauptanwendung, die Ressourcenvorlage zu laden.  Diese Vorlage wird tatsächlich in der DLL gespeichert.  Die Ursache besteht darin, dass Modulzustandsinformationen MFC nicht durch das Makro `AFX_MODULE_STATE` umgeschaltet wurden.  Das Ressourcenhandle wird von MFC Modulzustand wiederhergestellt.  Lässt das Umschalten nicht des Modulzustandes ein falsches Ressourcenhandle verwendet werden.  
  
 `AFX_MODULE_STATE` muss nicht, in jede Funktion in der DLL gespeichert werden.  Beispielsweise kann `InitInstance` von den MFC\-Code in der Anwendung ohne `AFX_MODULE_STATE`, da MFC automatisch den Modulzustand vor `InitInstance` und dann Schaltern es zurück bewegt, nachdem `InitInstance` zurückkehrt.  Das gilt für alle Meldungszuordnungshandler erfüllt.  Reguläre DLL belegt tatsächlich eine spezielle Vorlagenfensterprozedur, die automatisch den Modulzustand umschaltet, bevor eine Meldung weiterleitet.  
  
## Prozesslokale Daten  
 Prozesslokale Daten würden nicht von dieser großen Sorge kann er nicht für der Schwierigkeiten des Win32s\-DLL\-Modells gewesen sein.  In allen DLLs Win32\- geben Sie ihren globalen Daten, wenn geladen durch mehrere Anwendungen.  Dies ist mit dem "echten" Win32\-DLL\-Datenmodell sehr unterschiedlich, in dem jede DLL eine separate Kopie des Datenbereichs in jedem Prozess abruft, der an die DLL angefügt werden.  Um die Komplexität, sind die Daten, die auf dem Heap in einer Win32s\-DLL zugeordnet werden in Fakten\- Prozessbesondere \(mindestens insoweit Besitz geht\).  Betrachten Sie die folgenden Daten und den Code:  
  
```  
static CString strGlobal; // at file scope  
  
__declspec(dllexport)   
void SetGlobalString(LPCTSTR lpsz)  
{  
   strGlobal = lpsz;  
}  
  
__declspec(dllexport)  
void GetGlobalString(LPCTSTR lpsz, size_t cb)  
{  
   StringCbCopy(lpsz, cb, strGlobal);  
}  
```  
  
 Überlegen Sie, was geschieht, wenn der obige Code in einer DLL befindet und diese DLL durch zwei Prozesse A und B geladen wird \(es könnte zwei Instanzen derselben Anwendung tatsächlich sein\).  Aufrufe `SetGlobalString("Hello from A")`.  Daher wird für die `CString` Daten im Rahmen des Prozesses zugeordnet. A.  Beachten Sie, dass `CString` selbst global ist und zu A und zu B sichtbar ist.  Jetzt B ruft `GetGlobalString(sz, sizeof(sz))`.  B ist, die Daten darzustellen, die A festgelegt.  Dies ist, da Win32\- keinen Schutz zwischen Prozessen Win32 führt.  Das ist das erste Problem; in vielen Fällen ist es nicht wünschenswert, eine globale Daten des Anwendungsaffektes verfügen, die als zugehörige durch eine andere Anwendung angesehen wird.  
  
 Es gibt zusätzliche Probleme auch.  Nehmen wir beispielsweise an, dass A jetzt fertig.  Wenn A beendet, wird der Speicher, der durch die '`strGlobal`' \- Zeichenfolge verwendet wird, für das System bereitgestellt \- d. h Verarbeitung aller Speicher, der von zugeordnet wird, A wird freigegeben automatisch vom Betriebssystem.  Er wird nicht freigegeben, da der `CString` Destruktor aufgerufen wird; er noch nicht aufgerufen wurde.  Er wird einfach freigegeben, da die Anwendung, die ihm zugeordnet sind, die Szene verlassen hat.  Jetzt, wenn B `GetGlobalString(sz, sizeof(sz))`, wird möglicherweise keine gültigen Daten ab.  Eine andere Anwendung verwendet möglicherweise diesen Arbeitsspeicher für sonstige.  
  
 Natürlich müssen vorhanden ist ein Problem.  MFC 3.x verwendet eine Technik, lokalen Threadspeicher \(TLS\) aufgerufen wurde.  MFC 3.x würde einen TLS\-Index zuordnen, der unter Win32\- eigentlich als ein Speicherindex der Prozesslokalen Variable auftritt, obwohl er wird nicht aufgerufen, würde der und anschließend alle Daten auf diesem TLS\-Index verweisen.  Dies entspricht dem TLS\-Index ähnlich, der verwendet wurde, um als threadlokale Daten auf Win32 zu speichern \(siehe unten zu Informationen zu diesem Thema.\)  Dadurch gehen jede MFC\-DLL, zwei TLS\-Indizes pro Prozess mindestens zu verwenden.  Wenn Sie das Laden vieler OLE\-Steuerelement\-DLLs \(OCX\) anfordern, können Sie schnell mehr kein TLS\-Indizes \(es gibt nur 64 verfügbar\).  Außerdem musste MFC alle diese Daten in einem Raum, in einer einzelnen Struktur platzieren.  Es war nicht sehr erweiterbar und war nicht hinsichtlich ihres Nutzung von TLS\-Indizes ideal.  
  
 MFC 4.x behandelt dies mit einem Satz von Klassenvorlagen, die Sie die Daten "umschließen können" die Prozesslokale Variable sein sollten.  Zum Beispiel kann das Problem, das weiter oben erwähnt wurde, behoben werden, indem geschrieben hat:  
  
```  
struct CMyGlobalData : public CNoTrackObject  
{  
   CString strGlobal;  
};  
CProcessLocal<CMyGlobalData> globalData;  
  
__declspec(dllexport)   
void SetGlobalString(LPCTSTR lpsz)  
{  
   globalData->strGlobal = lpsz;  
}  
  
__declspec(dllexport)  
void GetGlobalString(LPCTSTR lpsz, size_t cb)  
{  
   StringCbCopy(lpsz, cb, globalData->strGlobal);  
}  
```  
  
 MFC implementiert dieses in zwei Schritten.  Zunächst ist eine Ebene für die Win32\- APIs **Tls\*** \(**TlsAlloc**, **TlsSetValue**, **TlsGetValue** usw.\), die nur zwei TLS\-Indizes pro Prozess verwenden unabhängig davon, wie viele DLLs Sie haben.  Zweitens ist die Vorlage `CProcessLocal` bereitgestellt, um auf diese Daten zuzugreifen.  Sie überschreibt, der \> Bediener ist, was die intuitive Syntax zulässig, die Sie weiter finden.  Alle Objekte, die von `CProcessLocal` umschlossen sind, müssen von `CNoTrackObject` abgeleitet werden.  `CNoTrackObject` stellt eine Zuweisung auf niedrigerer Ebene \(**LocalAlloc**\/**LocalFree**\) und einen virtuellen Destruktor so, dass MFC die lokalen ProzessObjekte automatisch zerstören kann, wenn der Prozess beendet wird.  Diese Objekte können ein benutzerdefinierter Destruktor verfügen, wenn zusätzliche Bereinigung erforderlich ist.  Das obige Beispiel erfordert kein, da der Compiler keinen Standarddestruktor generiert, um das `CString` eingebettete Objekt zu zerstören.  
  
 Es gibt weitere interessante Vorteile bei dieser Vorgehensweise.  Nicht nur werden alle `CProcessLocal`\-Objekte automatisch, werden sie erstellt nicht zerstört, bis sie benötigt werden.  `CProcessLocal::operator->` instanziiert das zugeordnete Objekt, wenn sie aufgerufen wird, und nicht früher.  Im Beispiel oben, dies bedeutet, dass die Zeichenfolge '`strGlobal`' nicht bis das erste Mal erstellt wird, **SetGlobalString** oder **GetGlobalString** aufgerufen wird.  In einigen Fällen kann dieses DLL\-Startzeit helfen, zu verringern.  
  
## Thread\-lokale Daten  
 Ähnlich den Daten, Prozesslokalen Threadlokale Daten wird verwendet, wenn die Daten in einen angegebenen Thread lokal sein müssen.  Das heißt, benötigen Sie eine separate Instanz der Daten für jeden Thread, der auf diese Daten zugegriffen wird.  Dies kann oft anstelle der umfangreichen Synchronisierungsmechanismen verwendet werden.  Wenn die Daten nicht erforderlich ist, von mehreren Threads gemeinsam genutzt wird, können diese Mechanismen aufwändig und nicht erforderlich sein.  Angenommen, wir ein `CString`\-Objekt hatten \(ähnlich wie im Beispiel oben\).  Wir können es Threadlokale Variablen ausführen, indem wir ihnen mit einer `CThreadLocal` \- Vorlage umschließen:  
  
```  
struct CMyThreadData : public CNoTrackObject  
{  
   CString strThread;  
};  
CThreadLocal<CMyThreadData> threadData;  
  
void MakeRandomString()  
{  
   // a kind of card shuffle (not a great one)  
   CString& str = threadData->strThread;  
   str.Empty();  
   while (str.GetLength() != 52)  
   {  
      unsigned int randomNumber;  
      errno_t randErr;  
      randErr = rand_s( &randomNumber );  
      if ( randErr == 0 )  
      {  
         TCHAR ch = randomNumber % 52 + 1;  
         if (str.Find(ch) < 0)  
            str += ch; // not found, add it  
      }  
   }  
}  
```  
  
 Wenn `MakeRandomString` von zwei verschiedenen Threads aufgerufen wurde, wird jedes die Zeichenfolge auf verschiedene Weise "verschmelzen" ohne das andere zu beeinflussen.  Dies ist, da er tatsächlich eine Instanz `strThread` pro Thread statt nur eine globale Instanz gibt.  
  
 Anstelle Hinweis, wie ein Verweis wird verwendet, um aufzuzeichnen einmal die `CString` einmal pro Schleifeniteration Adresse.  Der Schleifencode kann mit `threadData->strThread` eine '`str`' geschrieben worden sein wird verwendet, der Code ist in der Ausführung wesentlich langsamer sein.  Es empfiehlt sich, einen Verweis auf die Daten zwischenspeichern, wenn solche Verweise in den Schleifen auftreten.  
  
 Die `CThreadLocal`\-Klassenvorlage verwendet den gleichen Mechanismen, dass `CProcessLocal` ausführt und die gleichen Implementierungstechniken.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)