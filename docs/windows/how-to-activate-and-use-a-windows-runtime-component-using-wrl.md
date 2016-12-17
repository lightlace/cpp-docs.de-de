---
title: "Gewusst wie: Aktivieren und Verwenden einer Windows-Runtime-Komponente mit WRL"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Aktivieren und Verwenden einer Windows-Runtime-Komponente mit WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird gezeigt, wie Sie mit [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] initialisieren und eine [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Komponente aktivieren und verwenden.  
  
> [!NOTE]
>  In diesem Beispiel wird eine integrierte [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Komponente aktiviert.  Wie Sie eine eigene Komponente erstellen, die Sie auf ähnliche Weise aktivieren können, erfahren Sie unter [Exemplarische Vorgehensweise: Erstellen einer Basiskomponente für Windows\-Runtime](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md).  
  
 Um eine Komponente zu verwenden, müssen Sie einen Schnittstellenzeiger auf den Typ abrufen, der von der Komponente implementiert wird.  Und da die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] auf der COM\-Technologie \(Component Object Model\) basiert, müssen Sie eine Instanz des Typs nach den COM\-Regeln verwalten.  Beispielsweise müssen Sie den *Verweiszählerwert* verwalten, der bestimmt, wann der Typ aus dem Speicher gelöscht wird.  
  
 Um die Verwendung der [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] zu vereinfachen, stellt [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] die Vorlage für den intelligenten Zeigermechanismus, [ComPtr\<T\>](../windows/comptr-class.md), bereit, mit der die Verweiszählung automatisch ausgeführt wird.  Wenn Sie eine Variable deklarieren, geben Sie `ComPtr<`*interface\-name*`>` *identifier* an.  Um auf einen Schnittstellenmember zuzugreifen, wenden Sie den Pfeilmemberzugriffsoperator \(`->`\) auf den Bezeichner an.  
  
> [!IMPORTANT]
>  Wenn Sie eine Schnittstellenfunktion aufrufen, testen Sie stets den Rückgabewert `HRESULT`.  
  
## Aktivieren und Verwenden einer Windows Runtime\-Komponente  
 In den folgenden Schritten wird anhand der `Windows::Foundation::IUriRuntimeClass`\-Schnittstelle veranschaulicht, wie Sie eine Aktivierungsfactory für eine [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Komponente erstellen, eine Instanz dieser Komponente erstellen und einen Eigenschaftswert abrufen.  Sie zeigen außerdem, wie die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] initialisiert wird.  Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!IMPORTANT]
>  In der Regel verwenden Sie [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App; in diesem Beispiel wird jedoch zur Veranschaulichung eine Konsolen\-App verwendet.  Funktionen wie `wprintf_s` sind von einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App aus nicht verfügbar.  Weitere Informationen über die Typen und Funktionen, die Sie in einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App verwenden können, finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) und im Thema zu [Win32 und COM für Windows Store\-Apps](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
#### So aktivieren und verwenden Sie eine Windows Runtime\-Komponente  
  
1.  Schließen Sie \(mit `#include`\) alle erforderlichen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\- oder Standard\-C\+\+\-Bibliotheksheader ein.  
  
     [!CODE [wrl-consume-component#2](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#2)]  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`\-Direktive in der CPP\-Datei verständlicher zu gestalten.  
  
2.  Initialisieren Sie den Thread, in dem die App ausgeführt wird.  Jede App muss ihren Thread und ihr Threadingmodell initialisieren.  In diesem Beispiel wird mithilfe der Klasse [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] initialisiert und [RO\_INIT\_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) als Threadingmodell angegeben.  Die `RoInitializeWrapper`\-Klasse ruft `Windows::Foundation::Initialize` auf, wenn sie erstellt, und `Windows::Foundation::Uninitialize`, wenn sie zerstört wird.  
  
     [!CODE [wrl-consume-component#3](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#3)]  
  
     In der zweiten Anweisung gibt der Operator [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md)`HRESULT` vom Aufruf von `Windows::Foundation::Initialize` zurück.  
  
3.  Erstellen Sie eine *Aktivierungsfactory* für die `ABI::Windows::Foundation::IUriRuntimeClassFactory`\-Schnittstelle.  
  
     [!CODE [wrl-consume-component#4](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#4)]  
  
     Die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] identifiziert Typen anhand von voll qualifizierten Namen.  Der Parameter `RuntimeClass_Windows_Foundation_Uri` ist eine Zeichenfolge, die von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] bereitgestellt wird und den erforderlichen Ablaufklassennamen enthält.  
  
4.  Initialisieren Sie eine [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md)\-Variable, die den URI `"http://www.microsoft.com"` darstellt.  
  
     [!CODE [wrl-consume-component#6](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#6)]  
  
     In [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] belegen Sie für eine Zeichenfolge, die von der [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] verwendet wird, keinen Speicher.  Stattdessen erstellt die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] eine Kopie der Zeichenfolge in einem Puffer, den sie verwaltet und für Vorgänge verwendet, und gibt ein Handle für den erstellten Puffer zurück.  
  
5.  Erstellen Sie mit der `IUriRuntimeClassFactory::CreateUri`\-Factorymethode ein `ABI::Windows::Foundation::IUriRuntimeClass`\-Objekt.  
  
     [!CODE [wrl-consume-component#7](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#7)]  
  
6.  Rufen Sie die `IUriRuntimeClass::get_Domain`\-Methode auf, um den Wert der `Domain`\-Eigenschaft abzurufen.  
  
     [!CODE [wrl-consume-component#8](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#8)]  
  
7.  Drucken Sie den Domänennamen an die Konsole, und kehren Sie zurück.  Alle `ComPtr`\- und RAII\-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!CODE [wrl-consume-component#9](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#9)]  
  
     Die [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx)\-Funktion ruft das zugrunde liegende Unicode\-Formular der URI\-Zeichenfolge ab.  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!CODE [wrl-consume-component#1](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#1)]  
  
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-component.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe wrl\-consume\-component.cpp runtimeobject.lib**  
  
## Siehe auch  
 [Windows Runtime C\+\+ Template Library \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)