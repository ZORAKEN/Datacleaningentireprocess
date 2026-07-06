# Datacleaningentireprocess
a detailed summary of hiw data is cleaned,formatted including Customer funneling ,Sales analysis, Sales performance analysis,Customer segmentation
Most important code snippet:

** Identify data quality issues**
def data_quality_check(df):
    quality_report = {
        'total_records': len(df),
        'duplicate_rows': df.duplicated().sum(),
        'missing_values': df.isnull().sum().to_dict(),
        'invalid_emails': df[~df['email'].str.contains('@', na=False)].shape[0],
        'invalid_ages': df[(df['age'] < 0) | (df['age'] > 120)].shape[0]
    }
    return quality_report

quality_report = data_quality_check(df)
print(quality_report)
