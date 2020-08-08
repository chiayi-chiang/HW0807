# HW0807 select
/* 011
    列出店家目前提供那些餐點
    select r.rID,r.rName,m.mID,m.mName
    from restaurants r ,menus m
    where r.rID = m.rID
    ORDER By r.rID
/* 012
    列出店家賣出那些產品，各項餐點總收入為多少
    select r.rName,m.mName,d.Quantity,d.UnitPrice,(d.Quantity*d.UnitPrice)as total
    from restaurants r ,menus m ,details d
    where r.rID = m.rID AND m.mID = d.mID
    ORDER By r.rID
/* 013
    列出店家賣出那些產品，各項餐點是由誰買，由誰送單
    *同筆單，同一人送，同意人訂，但不同店家
    select r.rName,m.mName,o.oID,c.cName,c.Phone,c.Address,s.sName,s.sPhone
    from restaurants r ,menus m ,details d,orders o,customers c,shippers s
    where r.rID = m.rID 
	    AND m.mID = d.mID
        and d.oID = o.oID
        and o.cID = c.cID
        and o.sID = s.sID
    ORDER By r.rID
/* 021
    每位客人的訂單號，送單人，訂單日，送單日
    select c.cID,c.cName, o.oID,s.sName,s.sPhone, o.OrderDate,o.ShipDate 
    from restaurants r ,menus m ,details d ,orders o ,customers c ,shippers s
    where r.rID = m.rID 
        AND m.mID = d.mID
        and d.oID = o.oID
        and o.cID = c.cID
        and o.sID = s.sID
    ORDER BY c.cID
/* 022
    每位客人的訂單號和在各家店花費總額
    select c.cID,c.cName, o.oID,  d.mID,d.UnitPrice,d.Quantity,(d.UnitPrice * d.Quantity) as total
    from restaurants r ,menus m ,details d ,orders o ,customers c ,shippers s
    where r.rID = m.rID 
        AND m.mID = d.mID
        and d.oID = o.oID
        and o.cID = c.cID
        and o.sID = s.sID
    ORDER BY c.cID


