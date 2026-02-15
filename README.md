# Python-crawler-example
A basic Python crawler example for movie rankings.

# TMDB High-Rated Movie Ranking Crawler

This is a simple Python crawler project designed to scrape high-rated movie ranking data from the TMDB website. It is suitable for beginners to learn and practice web scraping.

## Project Structure
### 1. Core Modules
| Module Name | Function Description |
|-------------|----------------------|
| `requests`  | Send HTTP requests  |
| `csv`       | Data storage (CSV files) |
| `lxml`      | HTML page parsing   |

### 2. Main Functional Functions
| Function Name | Function Description |
|---------------|----------------------|
| `main()`      | Main process control<br>- Scrape movie lists by page (Pages 1-2)<br>- Traverse each movie to get detailed information<br>- Call the save function to store data |
| `get_movie_info(movie_info_url)` | Movie detail collection<br>- Parse the HTML of the movie detail page<br>- Use XPath positioning to get key information<br>- Return structured dictionary data |
| `save_all_movies(all_movies)`    | Data storage<br>- Write the list of dictionaries into a CSV file<br>- Use DictWriter to ensure field order<br>- Set UTF-8 encoding to support Chinese |

## Technical Points
### Crawler Strategy
- Pagination handling: Identify the website's pagination rules and use different URL strategies
  - Page 1: `TMDB_TOP_URL_1`
  - Page 2+: `TMDB_TOP_URL_2` + POST parameters

### XPath Positioning Skills
- Prioritize using the `id` attribute for precise positioning
- Combine the `class` attribute to obtain specific information
- Use the list index `[0]` to extract the first matching result

### Data Cleaning
- Null value handling: `if movie_names else ''`
- String cleaning: `.strip()` to remove leading and trailing spaces
- List merging: `','.join(movie_tags)` to convert multiple genre tags into a string

## Notes
1. Add `timeout=60` to prevent HTTP request timeouts
2. Set `newline=''` to avoid blank lines in the CSV file
3. The structure of movie detail pages may vary; adjust XPath expressions according to the actual page
4. Please comply with the website's `robots.txt` protocol when scraping data to avoid high-frequency requests
   
# TMDB 高分电影榜单爬虫

这是一个简单的 Python 爬虫项目，用于从 TMDB 网站爬取高分电影榜单数据，适合爬虫新手学习和实践。

## 项目结构
### 1. 核心模块
| 模块名 | 功能说明 |
|--------|----------|
| `requests` | 发送 HTTP 请求 |
| `csv` | 数据存储（CSV 文件） |
| `lxml` | HTML 页面解析 |

### 2. 主要功能函数
| 函数名 | 功能说明 |
|--------|----------|
| `main()` | 主流程控制<br>- 分页爬取电影列表（1-2页）<br>- 遍历每部电影，获取详情信息<br>- 调用保存功能存储数据 |
| `get_movie_info(movie_info_url)` | 电影详情采集<br>- 解析电影详情页 HTML<br>- 使用 XPath 定位获取关键信息<br>- 返回结构化字典数据 |
| `save_all_movies(all_movies)` | 数据存储<br>- 将字典列表写入 CSV 文件<br>- 使用 DictWriter 确保字段顺序<br>- 设置 UTF-8 编码支持中文 |

## 技术要点
### 爬虫策略
- 分页处理：识别网站分页规律，使用不同 URL 策略
  - 第1页：`TMDB_TOP_URL_1`
  - 第2+页：`TMDB_TOP_URL_2` + POST 参数

### XPath 定位技巧
- 优先使用 `id` 属性精准定位
- 结合 `class` 属性获取特定信息
- 使用列表索引 `[0]` 提取首个匹配结果

### 数据清洗
- 空值处理：`if movie_names else ''`
- 字符串清理：`.strip()` 去除首尾空格
- 列表合并：`','.join(movie_tags)` 将多类型标签转为字符串

## 注意事项
1. 添加 `timeout=60` 防止 HTTP 请求超时
2. 设置 `newline=''` 避免 CSV 文件出现空行
3. 电影详情页结构可能有差异，XPath 表达式需根据实际页面灵活调整
4. 爬取数据时请遵守网站 `robots.txt` 协议，避免高频请求
