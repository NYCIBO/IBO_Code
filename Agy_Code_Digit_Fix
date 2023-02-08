#Got the mayoralty showing as "2" instead of "002" because your CSV download dropped the zeros?
 
#create helper column. agency_cd is whichever field name has the agency code with an erratic number of digits.
df <- mutate(df, agy_cd_len = nchar(agency_cd))
 
#create conditional statement from nested ifelses. probably an inelegant solution if someone has something nicer
df <- mutate(df, agy_code = ifelse(agy_cd_len == 1, paste0("00",agency_cd), 
                             ifelse(agy_cd_len == 2, paste0("0",agency_cd), 
                                    agency_cd)))
 
#delete old column and helper column
df <- select(df, -c(agency_cd, agy_cd_len))
