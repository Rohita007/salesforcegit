CASE
  WHEN "indicator.Name" = 'Proxy Access' THEN 1
  WHEN EXISTS(SELECT 1 FROM "Authorizations" WHERE "indicator.Name" = 'Proxy Access') THEN
    CASE
      WHEN "indicator.Name" = 'Client Data Download' THEN 1
      WHEN "indicator.Name" = 'Fee Billing' THEN 1
      WHEN "indicator.Name" = 'Trading' THEN 1
      WHEN "indicator.Name" = 'Book of Business' THEN 0
      WHEN "indicator.Name" = 'View Only' THEN 0
      WHEN "indicator.Name" = 'Phone Inquiry Only' THEN 0
      ELSE 0
    END
  ELSE
    CASE
      WHEN "indicator.Name" = 'Client Data Download' THEN 0
      WHEN "indicator.Name" = 'Fee Billing' THEN 0
      WHEN "indicator.Name" = 'Trading' THEN 0
      WHEN "indicator.Name" = 'Book of Business' THEN 1
      WHEN "indicator.Name" = 'View Only' THEN 1
      WHEN "indicator.Name" = 'Phone Inquiry Only' THEN 1
      ELSE 0
    END
END
