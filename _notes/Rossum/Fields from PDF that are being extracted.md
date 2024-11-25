
`Id = docId,`

`Number = data.GetValue<string>("invoice_id"),`

`IssueDate = data.GetValue<DateTime?>("date_issue", dfi),`

`AcceptDate = data.GetValue<DateTime?>("date_accesptance", dfi),`

`CaseDate = data.GetValue<DateTime?>("date_case", dfi),`

`VATDate = data.GetValue<DateTime?>("date_uzp", dfi),`

`Description = data.GetValue<string>("description"),`

`Tag = data.GetValue<string>("internal_note"),`

`PartnerName = data.GetValue<string>("sender_name"),`

`PartnerAddress = data.GetValue<string>("sender_address"),`

`PartnerIC = data.GetValue<string>("sender_ic"),`

`PartnerVAT = data.GetValue<string>("sender_dic"),`

`PartnerLocalVAT = data.GetValue<string>("sender_local_vat"),`

`VariableSymbol = data.GetValue<string>("var_sym"),`

`ConstantSymbol = data.GetValue<string>("const_sym"),`

`SpecificSymbol = data.GetValue<string>("spec_sym"),`

`RoundingAmount = data.GetValue<decimal?>("amount_rounding", nfi),`

`AdvanceAmount = data.GetValue<decimal?>("amount_paid", nfi),`

`TotalAmount = data.GetValue<decimal?>("amount_due", nfi),`

`Currency = data.GetValue<string>("currency"),`

`ExchangeRate = data.GetValue<decimal?>("exchange_rate", nfi),`

`ExchangeRateUnits = data.GetValue<int?>("exchange_rate_units", nfi),`

`VATs = createVATs(data),`

`Lines = await createLines(data),`

`Accounting = createAccounting(data),`

`DoNotPay = getDoNotPayValue(data)`