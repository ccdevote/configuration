package com.qunar;

import com.google.common.base.Charsets;
import com.google.common.io.Files;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

import java.io.File;
import java.io.IOException;
import java.util.Map;

/**
 * Created by shaotianma on 14-5-9.
 */
public class MergeDate {
    public static final Logger LOG = LoggerFactory.getLogger(MergeDate.class);
    public static void main(String[] args) throws IOException {
        LOG.info(MergeDate.class.getResource("/data.txt").getFile());
        File data = new File(MergeDate.class.getResource("/data.txt").getFile());

        Map<MyDate, Integer> result = Files.readLines(data, Charsets.UTF_8, new FileLineProcessor());
        //输出
        Map.Entry<MyDate, Integer> start = null;
        Map.Entry<MyDate, Integer> pre = null;
        for (Map.Entry<MyDate, Integer> entry : result.entrySet()) {
            if(start == null) start = entry;
            if(pre == null) {
                pre = entry; continue;
            }
            MyDate nextDay = MyDateUtil.nextDay(pre.getKey());
            if(nextDay.equals(entry.getKey()) && pre.getValue().equals(entry.getValue())) {
                pre = entry; continue;
            } else {
                LOG.info(start.getKey() + "~" + entry.getKey() + " " + start.getValue());
                start = null;
                pre = entry;
            }
        }
        LOG.info(start.getKey() + "~" + pre.getKey() + " " + start.getValue());
    }

}
