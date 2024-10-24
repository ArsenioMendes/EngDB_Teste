@AbapCatalog.sqlViewName: 'ZCDSENGDBTESTE'
@AbapCatalog.compiler.compareFilter: true
@AbapCatalog.preserveKey: true
@AccessControl.authorizationCheck: #NOT_REQUIRED
@OData.publish: true
@EndUserText.label: 'Teste Engdb'
define view ZCDS_ENGDB_TESTE
  as select from j_1bnfdoc      as a

    inner join   j_1bnfe_active as b on b.docnum = a.docnum


{
  key a.docnum as NF_ID,
  a.bukrs  as EMPRESA,
  a.branch as FILIAL,
  a.nfenum as NUM_NFE,
  a.series as SERIE_NFE,
  a.parid  as CODIGO_DEST,
  a.vliq   as VAL_TOTAL,
  b.docsta as STATUS_SEFAZ,
  a.docdat as DATA

}
where
      a.cancel = ''
  and a.model  = '55';
