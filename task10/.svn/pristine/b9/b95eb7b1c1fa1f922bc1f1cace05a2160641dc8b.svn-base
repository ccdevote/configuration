package com.qunar;

import com.google.common.io.LineProcessor;

import java.io.IOException;
import java.util.Map;
import java.util.TreeMap;

/**
 * Created by shaotianma on 14-5-9.
 */
public class FileLineProcessor implements LineProcessor<Map<MyDate, Integer>> {
    Map<MyDate, Integer> map = new TreeMap<MyDate, Integer>();
    @Override public boolean processLine(String line) throws IOException {
        int sp1 = line.indexOf("～");
        if(sp1 == -1) return true;
        int sp2 = line.indexOf(" ", sp1);
        if(sp2 == -1) return true;
        //得到对应的字符串
        String startDate = line.substring(0, sp1);
        String endDate = line.substring(sp1 + 1, sp2);
        Integer price = Integer.parseInt(line.substring(sp2 + 1));
        //转化成对应的自定义的日期类型
        MyDate start = MyDateUtil.stringToMyDate(startDate);
        MyDate end = MyDateUtil.stringToMyDate(endDate);
        //System.out.println(start + "    " + end);
        for (MyDate i = start; i.compareTo(end) <= 0; i = MyDateUtil.nextDay(i)) {
            map.put(i, price);
        }
        return true;
    }

    @Override public Map<MyDate, Integer> getResult() {
        return map;
    }
}
