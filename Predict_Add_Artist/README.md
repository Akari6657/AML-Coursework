加上艺人分数特征
思路：
1) 按艺人统计历史平均排名 avg_rank、历史上榜天数 total_days（按艺人-日期去重）
2) 排名得分：score_rank = 1 - (avg_rank - 1) / 199   （排名越靠前，分越高）
3) 时长得分：score_days = total_days / max(total_days)
4) 综合得分：ArtistScore = a * score_rank + (1-a) * score_days
5) 多艺人歌曲：对参与艺人的 ArtistScore 取平均 → 歌曲级 Artist_Score

最后保留：id, Title, Artists, Nationality, 7个音频特征, Artist_Score, Rank, DaysOnChart
