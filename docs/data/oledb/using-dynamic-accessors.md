---
title: "Verwenden von dynamischen Accessoren"
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
  - "Accessoren [C++], dynamisch"
  - "Dynamische Accessoren"
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von dynamischen Accessoren
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dynamische Accessoren ermöglichen es Ihnen, auf eine Datenquelle zuzugreifen, wenn Ihnen das Datenbankschema \(die zugrunde liegende Struktur\) nicht bekannt ist.  Die OLE DB\-Vorlagenbibliothek enthält verschiedene Klassen, die Sie hierbei unterstützen.  
  
 Das Beispiel [DynamicConsumer](assetId:///2ccc4c61-6749-4e83-aa81-00f8009c0dc3) verdeutlicht, wie Sie mithilfe der dynamischen Accessorklassen Spalteninformationen abrufen und Accessoren dynamisch erstellen können.  
  
## Verwenden von CDynamicAccessor  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) ermöglicht es Ihnen, auf eine Datenquelle zuzugreifen, wenn Ihnen das Datenbankschema \(die zugrunde liegende Struktur\) nicht bekannt ist.  `CDynamicAccessor`\-Methoden beziehen Spalteninformationen \(z. B. Spaltennamen, Anzahl, Datentyp usw.\).  Sie verwenden diese Spalteninformationen, um einen Accessor zur Laufzeit dynamisch zu erstellen.  Die Spalteninformation wird in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird.  Ermitteln Sie Daten aus dem Puffer mithilfe der [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)\-Methode.  
  
## Beispiel  
  
### Code  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## Verwenden von CDynamicStringAccessor  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) funktioniert wie [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), jedoch mit einer wichtigen Ausnahme.  Während `CDynamicAccessor` Daten im vom Anbieter erfassten systemeigenen Format anfordert, fordert `CDynamicStringAccessor`, dass der Anbieter alle Daten, auf die über den Datenspeicher zugegriffen wird, als Zeichenfolgendaten abruft.  Dies ist besonders hilfreich für einfache Aufgaben, die keine Berechnungen von Werten im Datenspeicher erfordern, z. B. das Anzeigen oder Drucken des Datenspeicherinhalts.  
  
 Verwenden Sie `CDynamicStringAccessor`\-Methoden, um Spalteninformationen zu beziehen.  Sie verwenden diese Spalteninformationen, um einen Accessor zur Laufzeit dynamisch zu erstellen.  Die Spalteninformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird.  Rufen Sie Daten aus dem Puffer mithilfe von [CDynamicStringAccessor::GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) ab, oder speichern Sie sie mithilfe von [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md) im Puffer.  
  
## Beispiel  
  
### Code  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## Verwenden von CDynamicParameterAccessor  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) entspricht im Wesentlichen [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md). Der einzige Unterschied besteht darin, dass `CDynamicParameterAccessor` festzulegende Parameterinformationen durch Aufrufen der [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx)\-Schnittstelle bezieht.  Der Anbieter muss `ICommandWithParameters` für den Consumer unterstützen, damit diese Klasse verwendet werden kann.  
  
 Die Parameterinformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird.  Sie können Parameterdaten mithilfe von [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) und [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md) aus dem Puffer abrufen.  
  
 Ein Beispiel zur Demonstration der Verwendung dieser Klassen zum Ausführen einer gespeicherten SQL Server\-Prozedur sowie zum Abrufen der Ausgabeparameterwerte finden Sie im Knowledge Base\-Artikel Q058860, "HOWTO: Execute Stored Procedure using CDynamicParameterAccessor" \(nur auf Englisch verfügbar\). Knowledge Base\-Artikel sind in der MSDN Library Visual Studio\-Dokumentation oder an [http:\/\/support.microsoft.com](http://support.microsoft.com/) verfügbar.  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor\-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer Sample](assetId:///2ccc4c61-6749-4e83-aa81-00f8009c0dc3)